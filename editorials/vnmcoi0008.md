## 1. Xây dựng hệ phương trình

Ta cần xác định liệu có thể lấy hết số xu ở cả hai đống hay không. Trong mỗi lượt, ta có hai cách thực hiện:

- Lấy $1$ xu từ đống thứ nhất và $2$ xu từ đống thứ hai.
- Lấy $2$ xu từ đống thứ nhất và $1$ xu từ đống thứ hai.

Gọi $x$ là số lượt thực hiện cách thứ nhất và $y$ là số lượt thực hiện cách thứ hai.

Vì đống thứ nhất có $a$ xu và đống thứ hai có $b$ xu, để lấy hết xu ở cả hai đống, ta có hệ phương trình:

$$ \begin{cases} x + 2y = a \\\ 2x + y = b \end{cases} $$

Trong đó, $x,y$ phải là các số nguyên không âm vì chúng biểu diễn số lượt thực hiện mỗi thao tác.

## 2. Khai triển hệ phương trình

Từ phương trình đầu tiên:

$$ x + 2y = a $$

Ta suy ra:

$$ y = \frac{a-x}{2} $$

Tuy nhiên, để thuận tiện cho việc tính toán, ta có thể biểu diễn $y$ theo $x$ bằng cách bắt đầu từ phương trình:

$$ 2x+y=b $$

Suy ra:

$$ y=b-2x $$

Thay vào phương trình $x+2y=a$, ta được:

$$ x+2(b-2x)=a $$

Khai triển:

$$ x+2b-4x=a $$

$$ -3x=a-2b $$

Do đó:

$$ \boxed{x=\frac{2b-a}{3}} $$

Sau khi tìm được $x$, ta tính:

$$ \boxed{y=b-2x} $$

Để nghiệm hợp lệ, cần thỏa mãn hai điều kiện:

- $2b-a$ chia hết cho $3$, để $x$ là số nguyên.
- $x \ge 0$ và $y \ge 0$, vì số lượt thực hiện mỗi thao tác không thể âm.

Nếu cả hai điều kiện đều được thỏa mãn, in `YES`; ngược lại, in `NO`.

```cpp
#include <bits/stdc++.h>
using namespace std;

void solve(void)
{
    int a, b;
    cin >> a >> b;
    int x = (b - 2 * a) / -3;
    if ((b - 2 * a) % 3 != 0)
    {
        cout << "NO\n";
    }
    else
    {
        int y = a - 2 * x;
        if (y < 0 || x < 0)
        {
            cout << "NO\n";
        }
        else
        {
            cout << "YES\n";
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