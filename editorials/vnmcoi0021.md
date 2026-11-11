## Ý tưởng

Để giải quyết bài toán, trước hết chúng ta cần sử dụng công thức tính tổ hợp:

$$
\binom{a}{b}=\frac{a!}{b!(a-b)!}
$$

Tuy nhiên, bài toán yêu cầu tính kết quả theo modulo $10^9+7$. Khi thực hiện phép chia trong modulo, chúng ta không thể sử dụng phép chia thông thường mà phải thay thế bằng **nghịch đảo modulo**.

## Nghịch đảo modulo

Giả sử $p$ là một số nguyên tố. Theo định lý nhỏ Fermat, với mọi số nguyên $x$ thỏa mãn $x\not\equiv 0\pmod p$, ta có:

$$
x^{p-1}\equiv 1\pmod p
$$

Chia cả hai vế cho $x$, hay tương đương với nhân hai vế với nghịch đảo modulo của $x$, ta thu được:

$$
x^{p-2}\equiv x^{-1}\pmod p
$$

Do đó, nghịch đảo modulo của $x$ có thể được tính bằng:

$$
\boxed{x^{-1}\equiv x^{p-2}\pmod p}
$$

Trong bài toán này, $p=10^9+7$ là một số nguyên tố.

Vì vậy, nếu $x$ không chia hết cho $p$, ta có thể tính nghịch đảo modulo của $x$ bằng cách tính $x^{p-2}\pmod p$.

Tuy nhiên, số mũ $p-2$ rất lớn. Nếu sử dụng vòng lặp thông thường để nhân $x$ với chính nó $p-2$ lần, độ phức tạp sẽ là $O(p)$, không đáp ứng được yêu cầu của bài toán.

Thay vào đó, chúng ta sử dụng **lũy thừa nhị phân** để tính lũy thừa modulo trong thời gian $O(\log p)$.

## Tính tổ hợp

Từ công thức ban đầu:

$$
\binom{a}{b}=\frac{a!}{b!(a-b)!}
$$

Ta có thể viết lại dưới dạng:

$$
\binom{a}{b}
=
a!\cdot (b!)^{-1}\cdot ((a-b)!)^{-1}
$$

Với $p=10^9+7$, áp dụng định lý nhỏ Fermat:

$$
\binom{a}{b}
\equiv
a!\cdot (b!)^{p-2}\cdot ((a-b)!)^{p-2}
\pmod p
$$

Do có nhiều truy vấn và $a\le 10^6$, chúng ta có thể tiền xử lý giai thừa modulo $p$ cho tất cả các giá trị cần thiết.

Đặt:

$$
fact[i]=i!\pmod p
$$

Ta có công thức truy hồi:

$$
fact[0]=1
$$

$$
fact[i]=fact[i-1]\cdot i\pmod p
$$

Sau khi tiền xử lý, mỗi truy vấn $(a,b)$ được trả lời bằng công thức:

$$
\boxed{
\binom{a}{b}
\equiv
fact[a]\cdot
fact[b]^{p-2}\cdot
fact[a-b]^{p-2}
\pmod p
}
$$

Hai phép tính lũy thừa được thực hiện bằng lũy thừa nhị phân.

## Độ phức tạp

Gọi $N$ là giá trị lớn nhất của $a$, và $n$ là số truy vấn.

- Tiền xử lý giai thừa: $O(N)$.
- Mỗi truy vấn: $O(\log p)$.
- Tổng độ phức tạp thời gian: $O(N+n\log p)$.
- Độ phức tạp bộ nhớ: $O(N)$.

Với $N\le 10^6$, $n\le 10^5$ và $p=10^9+7$, phương pháp này đáp ứng được các giới hạn của bài toán.

**Lưu ý:** Đây không phải cách duy nhất để tính nghịch đảo modulo. Bạn có thể tìm hiểu thêm các phương pháp khác, chẳng hạn như thuật toán Euclid mở rộng hoặc tiền xử lý nghịch đảo modulo. Với bài toán này, sử dụng định lý nhỏ Fermat kết hợp lũy thừa nhị phân là một phương pháp đơn giản và dễ triển khai.


```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e6 + 5;
const int MOD = 1e9 + 7;

int p[mxN];

int binpow(int a, int n)
{
    int res = 1;
    while (n > 0)
    {
        if (n & 1)
        {
            res = 1LL * res * a % MOD;
        }
        a = 1LL * a * a % MOD;
        n >>= 1;
    }
    return res % MOD;
}

void init(void)
{
    p[0] = 1;
    for (int i = 1; i < mxN; ++i)
    {
        p[i] = 1LL * i * p[i - 1] % MOD;
    }
}

void solve(void)
{
    int a, b;
    cin >> a >> b;
    cout << (1LL * p[a] * binpow(p[b], MOD - 2) % MOD) * binpow(p[a - b], MOD - 2) % MOD << '\n';
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    init();
    int n;
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        solve();
    }
    return 0;
}
```