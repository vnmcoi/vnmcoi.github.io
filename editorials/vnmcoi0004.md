Để giải bài toán này, ta cần tìm quy luật phân bố các số trong number spiral dựa trên tọa độ hàng $y$ và cột $x$.

Đặt $m = \max(y, x)$. Các ô nằm trên đường viền của hình vuông có cạnh dài $m$ chứa các giá trị từ $(m - 1)^2 + 1$ đến $m^2$. Do đó, ta có thể bắt đầu từ giá trị lớn nhất $m^2$ rồi tính độ chênh lệch dựa trên vị trí của ô cần tìm.

Có bốn trường hợp cần xét, tùy thuộc vào việc $y$ hay $x$ lớn hơn và tính chẵn lẻ của tọa độ lớn hơn. Trong mỗi trường hợp, hướng tăng của các số trên đường viền sẽ quyết định cách tính giá trị tại ô $(y, x)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

void solve(void)
{
    int y, x;
    cin >> y >> x;
    int mx = max(y, x);
    if (mx == y)
    {
        if (y % 2 == 0)
        {
            cout << 1LL * mx * mx - (x - 1) << '\n';
        }
        else
        {
            cout << 1LL * mx * mx - y - (y - 1 - x) << '\n';
        }
    }
    else
    {
        if (x % 2 == 0)
        {
            cout << 1LL * mx * mx - x - (x - 1 - y) << '\n';
        }
        else
        {
            cout << 1LL * mx * mx - (y - 1) << '\n';
        }
    }
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;
    for (int i = 1; i <= t; ++i)
    {
        solve();
    }
    return 0;
}
```