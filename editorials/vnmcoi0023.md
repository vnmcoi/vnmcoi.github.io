Để giải quyết bài toán này, trước hết chúng ta cần nhắc lại về **định lý nhỏ Fermat**.

Với $p$ là một số nguyên tố và $a$ là một số nguyên không chia hết cho $p$, ta có:

$$
a^{p-1}\equiv 1\pmod p
$$

Từ đó, với $k$ là một số nguyên không âm, ta có thể rút gọn số mũ:

$$
a^k\equiv a^{k\bmod(p-1)}\pmod p
$$

Điều này giúp chúng ta tính lũy thừa với số mũ rất lớn một cách hiệu quả.

## Ví dụ minh họa

Xét bài toán:

$$
3^{100}\pmod 7
$$

Theo định lý nhỏ Fermat, ta có:

$$
3^6\equiv 1\pmod 7
$$

Ta phân tích số mũ:

$$
100=6\times16+4
$$

Do đó:

$$
\begin{aligned}
3^{100}
&=3^{6\times16+4}\\
&=(3^6)^{16}\times3^4\\
&\equiv 1^{16}\times3^4\\
&\equiv 4\pmod 7
\end{aligned}
$$

Như vậy, thay vì tính trực tiếp $3^{100}$, chúng ta chỉ cần tính $3^4\pmod 7$.

## Áp dụng vào bài toán

Bài toán yêu cầu tính:

$$
a^{b^c}\pmod {10^9+7}
$$

Đặt:

$$
MOD=10^9+7
$$

Vì $MOD$ là một số nguyên tố, theo định lý nhỏ Fermat, nếu $a$ không chia hết cho $MOD$, ta có thể rút gọn số mũ:

$$
a^{b^c}\equiv
a^{b^c\bmod(MOD-1)}
\pmod {MOD}
$$

Do đó, chúng ta chia bài toán thành hai bước:

**Bước 1:** Tính:

$$
k=b^c\bmod(MOD-1)
$$

**Bước 2:** Tính:

$$
ans=a^k\bmod MOD
$$

Cả hai phép tính đều có thể được thực hiện bằng thuật toán **lũy thừa nhị phân** với độ phức tạp $O(\log MOD)$.

**Lưu ý:** Công thức rút gọn số mũ ở trên chỉ áp dụng trực tiếp khi $a\not\equiv 0\pmod {MOD}$. Vì vậy, chúng ta cần xử lý riêng trường hợp $a=0$, đồng thời tuân theo quy ước $0^0=1$ của đề bài.

Với trường hợp $a=0$:

- Nếu $b=0$ và $c>0$, ta có $b^c=0$, nên kết quả là $0^0=1$.
- Nếu $b>0$ và $c=0$, ta cũng có $b^c=1$, nên kết quả là $0^1=0$.
- Nếu $b>0$ và $c>0$, kết quả là $0$.
- Nếu $b=0$ và $c=0$, ta có $b^c=0^0=1$, nên kết quả là $0^1=0$.

## Độ phức tạp

Mỗi truy vấn cần thực hiện hai lần lũy thừa nhị phân:

- Tính $b^c\bmod(MOD-1)$: $O(\log c)$.
- Tính $a^k\bmod MOD$: $O(\log MOD)$.

Do đó, với $n$ truy vấn, tổng độ phức tạp thời gian là:

$$
O(n(\log c+\log MOD))
$$

Độ phức tạp bộ nhớ phụ trợ là $O(1)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int MOD = 1e9 + 7;

int binpow(int a, int n, int m)
{
    int res = 1;
    for (; n > 0; n >>= 1)
    {
        if (n & 1)
        {
            res = 1LL * res * a % m;
        }
        a = 1LL * a * a % m;
    }
    return res;
}

void solve(void)
{
    int a, b, c;
    cin >> a >> b >> c;
    cout << binpow(a, binpow(b, c, MOD - 1), MOD) << '\n';
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