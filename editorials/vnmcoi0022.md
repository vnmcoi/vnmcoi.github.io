Để tính nhanh được $a^b \bmod 10^9 + 7$ thì ta có thể  sử dụng phép lũy thừa nhị phân.

Ta thấy rằng khi thực hiện phân tích mũ $b$ của cơ số $a$ dưới dạng nhị phân thì chúng ta sẽ có một tính chất đặc biệt.

Ví dụ: Chúng ta cần tính $5^{13}$.

$13_{10} = 1101_2$

Khi này thì ta có thể tách kết quả cần tính ra thành:

$$
5^{15} = 5^{1000_{2}} \times 5^{100_{2}} \times 5^{10_{2}} \times 5^{1_{2}} = 5^8 \times 5^4 \times 5^2 \times 5^1
$$

Câu chuyện bây giờ là tính $a^b$ sau phân tách như thế nào?

Ta thấy rằng với mỗi lần thì hệ số mũ của $b$ tăng gấp đôi so với lần trước đó.

$$
5^{15} = (5^4 \times 5^4) \times (5^2 \times 5^2) \times (5^1 \times 5^1) \times (5^1)
$$

Và chúng ta sẽ bắt đầu với $a^1 = 5^1$ rồi các hệ số $a$ của bước sau chính là $a \times a$ với $a$ ở đây là giá trị của $a$ bước trước.

Nếu trong phân tích bit của hệ số $b$ là một số lẻ thì ta thực hiện nhân giá trị đó vào kết quả cuối cùng.

Độ phức tạp thời gian: $\mathcal{O} (\log b)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int MOD = 1e9 + 7;

int binpow(int a, int n)
{
    int res = 1;
    for (; n > 0; n >>= 1)
    {
        if (n & 1)
        {
            res = 1LL * res * a % MOD;
        }
        a = 1LL * a * a % MOD;
    }
    return res;
}

void solve(void)
{
    int a, b;
    cin >> a >> b;
    cout << binpow(a, b) << '\n';
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
