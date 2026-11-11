MEX (Minimum Excluded) là số nguyên không âm nhỏ nhất không xuất hi\mathcal {O} Oện trong một tập hợp các giá trị.

Trong bài toán này, giá trị tại ô $(i,j)$ là MEX của các phần tử nằm bên trái ô đó trên cùng hàng $i$ và phía trên ô đó trên cùng cột $j$.

Vì $n \le 100$, ta có thể xây dựng ma trận lần lượt từ trái sang phải, từ trên xuống dưới. Khi xét ô $(i,j)$, tất cả các ô cần kiểm tra đều đã được tính trước đó.

Cụ thể, ta sử dụng một mảng đánh dấu `vis` để lưu những giá trị đã xuất hiện:

- Duyệt các ô phía trên $(i,j)$ trong cột $j$ và đánh dấu giá trị của chúng.
- Duyệt các ô bên trái $(i,j)$ trong hàng $i$ và đánh dấu giá trị của chúng.
- Bắt đầu từ $v = 0$, tăng $v$ cho đến khi tìm được giá trị chưa được đánh dấu. Đây chính là MEX cần điền vào ô $(i,j)$.

Sau khi tính xong toàn bộ ma trận, ta in các phần tử theo từng hàng.

Với mỗi ô, ta duyệt tối đa $\mathcal {O} (n)$ phần tử để tìm MEX, và có tổng cộng $\mathcal {O} (n^2)$ ô. Vì vậy, độ phức tạp thời gian là $\mathcal {O} (n^3)$, còn độ phức tạp bộ nhớ phụ là $\mathcal {O} (n)$. Với giới hạn $n \le 100$, cách tiếp cận này hoàn toàn đáp ứng yêu cầu bài toán.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e2 + 5;

int N;
int A[mxN][mxN];
bool vis[2 * mxN];

void solve(void)
{
    cin >> N;
    for (int i = 1; i <= N; ++i)
    {
        for (int j = 1; j <= N; ++j)
        {
            memset(vis, false, sizeof(vis));
            for (int x = i - 1; x >= 1; --x)
            {
                vis[A[x][j]] = true;
            }
            for (int y = j - 1; y >= 1; --y)
            {
                vis[A[i][y]] = true;
            }
            int v = 0;
            while (vis[v] == true)
            {
                ++v;
            }
            A[i][j] = v;
        }
    }
    for (int i = 1; i <= N; ++i)
    {
        for (int j = 1; j <= N; ++j)
        {
            cout << A[i][j] << ' ';
        }
        cout << '\n';
    }
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```