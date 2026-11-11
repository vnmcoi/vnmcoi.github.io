Ta sử dụng quay lui (Backtracking) để tìm tất cả các cách đặt $8$ quân hậu sao cho không có hai quân hậu nào tấn công lẫn nhau.

Tuy nhiên, nếu thử đặt quân hậu vào tất cả các ô trên bàn cờ thì số lượng trường hợp cần xét sẽ rất lớn. Vì vậy, ta sẽ tối ưu quá trình tìm kiếm bằng cách tận dụng các tính chất của quân hậu.

## Tối ưu hóa 1: Cố định thứ tự đặt quân hậu

Quân hậu có thể tấn công các ô nằm cùng hàng, cùng cột hoặc cùng đường chéo.

Do đó, mỗi hàng chỉ có thể chứa tối đa một quân hậu. Ta có thể cố định thứ tự đặt quân hậu theo từng hàng, từ hàng $1$ đến hàng $8$.

Ở mỗi hàng, ta thử đặt quân hậu vào từng cột có thể. Nếu ô đang xét là ô bị cấm (`*`), ta bỏ qua ô đó.

Nhờ cố định thứ tự theo hàng, ta không cần kiểm tra xem các quân hậu đã đặt có nằm cùng hàng hay không, vì mỗi hàng chỉ được đặt đúng một quân hậu.

## Tối ưu hóa 2: Kiểm tra đường chéo bằng mảng đánh dấu

Để kiểm tra các quân hậu có nằm cùng đường chéo hay không, ta có thể sử dụng hai mảng đánh dấu.

Gọi $x,y$ lần lượt là tọa độ hàng và cột của một ô.

Đường chéo chính:

Các ô nằm trên cùng một đường chéo chính có hiệu giữa tọa độ hàng và cột không đổi:

$$ x-y=\text{constant} $$

Ví dụ, hai ô $(x,y)$ và $(x+n,y+n)$ nằm trên cùng một đường chéo chính.

Đường chéo phụ:

Các ô nằm trên cùng một đường chéo phụ có tổng tọa độ hàng và cột không đổi:

$$ x+y=\text{constant} $$

Ví dụ, hai ô $(x,y)$ và $(x+n,y-n)$ nằm trên cùng một đường chéo phụ.

Ta sử dụng hai mảng:

- `diag1` đánh dấu các đường chéo chính.
- `diag2` đánh dấu các đường chéo phụ.

Vì giá trị $x-y$ có thể âm, ta cộng thêm $8$ để chuyển chỉ số về miền không âm.

Với mỗi ô $(x,y)$, ta kiểm tra:

- Ô đó có bị cấm hay không.
- Cột $y$ đã có quân hậu nào chưa.
- Đường chéo chính $x+y$ đã có quân hậu nào chưa.
- Đường chéo phụ $x-y+8$ đã có quân hậu nào chưa.

Nếu cả bốn điều kiện đều thỏa mãn, ta đặt quân hậu tại ô đó, đánh dấu cột và hai đường chéo tương ứng, sau đó tiếp tục đệ quy sang hàng tiếp theo.

Khi quay lui, ta bỏ các đánh dấu để thử những vị trí khác.

### Điều kiện kết thúc

Khi đã đặt được quân hậu ở cả $8$ hàng, ta tìm được một cách đặt hợp lệ. Khi đó, tăng biến đếm `ans` lên $1$.

Sau khi quá trình quay lui kết thúc, `ans` chính là số cách đặt $8$ quân hậu thỏa mãn các điều kiện của đề bài.

Độ phức tạp:

- Thời gian: $\mathcal {O} (8!)$ trong trường hợp xấu nhất, do mỗi hàng chọn một cột khác nhau. Việc kiểm tra cột và đường chéo được thực hiện trong $\mathcal {O} (1)$.
- Bộ nhớ: $\mathcal {O} (8)$ cho các mảng đánh dấu và ngăn xếp đệ quy.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 8;

int ok[mxN + 1][mxN + 1], col[mxN + 1], diag1[2 * mxN + 1], diag2[2 * mxN + 1];
int ans = 0;

void wayslui(int n)
{
    if (n == 9)
    {
        ++ans;
        return;
    }
    for (int y = 1; y <= 8; ++y)
    {
        if (ok[n][y] == false && col[y] == false && diag1[n + y] == false && diag2[n - y + mxN] == false)
        {
            col[y] = true;
            diag1[n + y] = true;
            diag2[n - y + mxN] = true;
            wayslui(n + 1);
            col[y] = false;
            diag1[n + y] = false;
            diag2[n - y + mxN] = false;
        }
    }
}

void solve(void)
{
    for (int i = 1; i <= mxN; ++i)
    {
        string S;
        cin >> S;
        for (int j = 0; j < mxN; ++j)
        {
            if (S[j] == '*')
            {
                ok[i][j + 1] = true;
            }
        }
    }
    wayslui(1);
    cout << ans;
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```