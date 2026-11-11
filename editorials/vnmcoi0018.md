## Ý tưởng

Ta sử dụng quay lui (Backtracking) để tìm tất cả các đường đi hợp lệ trên bàn cờ $7 \times 7$, từ ô góc trên bên trái $(1,1)$ đến ô góc dưới bên trái $(7,1)$.

Mỗi đường đi phải đi qua tất cả $49$ ô đúng một lần, tức là đường đi có tổng cộng $48$ bước. Tại mỗi bước, ta có thể di chuyển theo một trong bốn hướng: xuống (`D`), lên (`U`), phải (`R`) hoặc trái (`L`). Nếu ký tự tương ứng trong xâu đầu vào là `?`, ta được phép đi theo bất kỳ hướng nào.

Nếu thử tất cả các hướng đi có thể tại mỗi bước, số trường hợp cần xét sẽ rất lớn. Vì vậy, ta cần áp dụng một số điều kiện cắt nhánh để loại bỏ những đường đi không thể tạo thành lời giải hợp lệ.

## Tối ưu hóa 1: Kiểm tra điều kiện kết thúc

Vì đường đi phải đi qua tất cả các ô đúng một lần, nên nếu ta đã đến ô đích $(7,1)$ trước khi đi đủ $48$ bước thì đường đi đó không hợp lệ.

Ngược lại, nếu đi đủ $48$ bước mà chưa đến ô đích thì cũng không thể tạo thành một đường đi hợp lệ.

Do đó, khi đến ô đích, ta chỉ tăng biến đếm `ans` nếu đã đi đủ $48$ bước, sau đó kết thúc nhánh đệ quy hiện tại.

## Tối ưu hóa 2: Phát hiện đường đi chia cắt bàn cờ

Đây là một tối ưu hóa quan trọng giúp giảm đáng kể số trường hợp cần xét.

Ta xét vị trí hiện tại của đường đi. Nếu đường đi đã chia các ô chưa thăm thành hai vùng độc lập, không còn cách nào di chuyển giữa hai vùng mà không đi qua ô đã thăm, thì ta không thể hoàn thành đường đi.

Ví dụ, nếu:

- Ô phía trên và phía dưới vị trí hiện tại đều đã được thăm.
- Hai ô bên trái và bên phải vẫn chưa được thăm.

Khi đó, các ô chưa thăm ở hai bên bị chia thành hai vùng riêng biệt. Ta không thể đi qua cả hai vùng mà không quay lại ô hiện tại, điều này vi phạm điều kiện mỗi ô chỉ được đi qua một lần.

Tương tự, nếu hai ô bên trái và bên phải đã được thăm, nhưng hai ô phía trên và phía dưới vẫn chưa được thăm, ta cũng có thể loại bỏ nhánh hiện tại.

Trong code, ta kiểm tra hai trường hợp này bằng mảng `vis` để đánh dấu các ô đã được đi qua.

## Tối ưu hóa 3: Đánh dấu các ô ngoài bàn cờ

Ta đánh dấu các ô nằm ngoài bàn cờ là đã được thăm.

Nhờ đó, khi kiểm tra các hướng di chuyển, ta không cần phải liên tục kiểm tra xem tọa độ mới có vượt ra ngoài bàn cờ hay không. Các ô ngoài bàn cờ sẽ tự động bị loại bỏ bởi điều kiện `vis`.

## Quá trình quay lui

Hàm đệ quy `dewuy(n, x, y)` có ý nghĩa:

- $n$ là bước di chuyển hiện tại.
- $(x,y)$ là vị trí hiện tại của đường đi.

Ở mỗi bước, ta thử các hướng di chuyển được cho phép bởi ký tự `S[n]`.

Nếu ô tiếp theo chưa được thăm, ta đánh dấu ô đó, gọi đệ quy để tiếp tục tìm kiếm, sau đó bỏ đánh dấu khi quay lui.

Khi hoàn thành quá trình tìm kiếm, `ans` chính là số đường đi thỏa mãn mô tả đầu vào.

Độ phức tạp:

- Thời gian: Trong trường hợp xấu nhất, quay lui có thể xét một số lượng đường đi rất lớn. Các điều kiện cắt nhánh giúp giảm đáng kể số trường hợp thực tế.
- Bộ nhớ: $\mathcal {O} (48)$ cho ngăn xếp đệ quy và mảng đánh dấu bàn cờ $7 \times 7$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 7 + 5;

bitset<mxN> vis[mxN];
string S;
int ans = 0;

void dewuy(int n, int x, int y)
{
    if (x == 7 && y == 1)
    {
        if (n == 49)
        {
            ++ans;
        }
        return;
    }
    if (vis[x + 1][y] == true && vis[x - 1][y] == true && vis[x][y + 1] == false && vis[x][y - 1] == false)
    {
        return;
    }
    if (vis[x + 1][y] == false && vis[x - 1][y] == false && vis[x][y + 1] == true && vis[x][y - 1] == true)
    {
        return;
    }
    if ((S[n] == 'D' || S[n] == '?') && vis[x + 1][y] == false && x + 1 <= 7)
    {
        vis[x + 1][y] = true;
        dewuy(n + 1, x + 1, y);
        vis[x + 1][y] = false;
    }
    if ((S[n] == 'U' || S[n] == '?') && vis[x - 1][y] == false && x - 1 >= 1)
    {
        vis[x - 1][y] = true;
        dewuy(n + 1, x - 1, y);
        vis[x - 1][y] = false;
    }
    if ((S[n] == 'R' || S[n] == '?') && vis[x][y + 1] == false && y + 1 <= 7)
    {
        vis[x][y + 1] = true;
        dewuy(n + 1, x, y + 1);
        vis[x][y + 1] = false;
    }
    if ((S[n] == 'L' || S[n] == '?') && vis[x][y - 1] == false && y - 1 >= 1)
    {
        vis[x][y - 1] = true;
        dewuy(n + 1, x, y - 1);
        vis[x][y - 1] = false;
    }
}

void solve(void)
{
    cin >> S;
    S = ' ' + S;
    vis[1][1] = true;
    for (int i = 0; i <= 8; ++i)
    {
        vis[i][0] = vis[0][i] = vis[i][8] = vis[8][i] = true;
    }
    dewuy(1, 1, 1);
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