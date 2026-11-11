Để giải quyết bài toán, trước hết chúng ta nhận thấy rằng nếu tìm được một ước của số $x$, gọi là $a$, thì ta cũng có thể tìm được ước số còn lại bằng công thức:
$$
b=\frac{x}{a}
$$

Hay nói cách khác:
$$
a\times b=x
$$

Vậy chúng ta có thể duyệt qua tất cả các giá trị $a$ từ $1$ đến $x$. Nếu $x$ chia hết cho $a$, ta tìm được một ước số của $x$.

Từ đó, ta chỉ cần đếm số lượng các giá trị thỏa mãn điều kiện:
$$
x\bmod a=0
$$

Độ phức tạp thời gian của phương pháp này là: $\mathcal {O} (x)$

Tối ưu hóa
Ta nhận thấy rằng việc duyệt toàn bộ các giá trị từ $1$ đến $x$ là không cần thiết, bởi vì các ước số của một số nguyên luôn có tính chất đối xứng.

Cụ thể, nếu $a$ là một ước của $x$, thì:
$$
b=\frac{x}{a}
$$

cũng là một ước của $x$.

Từ đó, ta có thể ghép các ước số thành từng cặp:
$$
\left(a,\frac{x}{a}\right)
$$

Xét mối quan hệ giữa hai ước số trong một cặp:
- Nếu $a < \sqrt{x}$, thì $\frac{x}{a} > \sqrt{x}$.
- Nếu $a > \sqrt{x}$, thì $\frac{x}{a} < \sqrt{x}$.
- Nếu $a = \sqrt{x}$, thì $x$ là một số chính phương và hai ước số trong cặp trùng nhau.
Như vậy, mỗi cặp ước số luôn có ít nhất một phần tử không vượt quá $\sqrt{x}$.

Do đó, thay vì duyệt toàn bộ các giá trị từ $1$ đến $x$, chúng ta chỉ cần duyệt từ:
$$
[1,\sqrt{x}]
$$

Với mỗi giá trị $i$, nếu:
$$
x\bmod i=0
$$

thì ta tìm được một cặp ước số:
$$
\left(i,\frac{x}{i}\right)
$$

Khi đó, ta tăng kết quả thêm $2$.

Tuy nhiên, nếu $i=\frac{x}{i}$, tức là $x$ là số chính phương và $i=\sqrt{x}$, ta chỉ tăng kết quả thêm $1$ để tránh đếm trùng.

Độ phức tạp thời gian sau khi tối ưu: $\mathcal {O} (\sqrt{x})$.

Với $n$ truy vấn, tổng độ phức tạp thời gian là: $\mathcal {\mathcal {O} } (n \times \sqrt{x})$

```cpp
#include <bits/stdc++.h>
using namespace std;

void solve(void)
{
    int x;
    cin >> x;
    int ans = 0;
    for (int i = 1; i * i <= x; ++i)
    {
        if (x % i == 0)
        {
            ++ans;
            if (i != x / i)
            {
                ++ans;
            }
        }
    }
    cout << ans << '\n';
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n;
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        solve();
    }
    return 0;
}
```