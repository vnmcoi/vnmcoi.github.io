Ta cần chứng minh rằng giá trị $x$ làm cực tiểu hàm:
$$
f(x)=|x-p_1|+|x-p_2|+\cdots+|x-p_n|
$$

chính là trung vị của dãy số.

Không mất tính tổng quát, giả sử:

$$
p_1\le p_2\le \cdots\le p_n
$$

Xét việc thay đổi $x$ một lượng rất nhỏ $\Delta x>0$.

Khi $x$ tăng thêm $\Delta x$:
- Với mỗi $p_i<x$, khoảng cách $|x-p_i|$ tăng thêm $\Delta x$.
- Với mỗi $p_i>x$, khoảng cách $|x-p_i|$ giảm đi $\Delta x$.

Gọi:

- $L$ là số phần tử nhỏ hơn $x$.
- $R$ là số phần tử lớn hơn $x$.

Khi đó, nếu $x$ không trùng với bất kỳ $p_i$ nào, ta có:
$$
f(x+\Delta x)-f(x)
=(L-R)\Delta x
$$

Đây chính là điểm mấu chốt.

Có ba trường hợp:

Trường hợp 1: $L<R$
$$
f(x+\Delta x)-f(x)<0
$$

Tức là khi tăng $x$, hàm số giảm.

Điều này có nghĩa là $x$ vẫn đang nằm về phía bên trái của vùng tối ưu.

Trường hợp 2: $L>R$
$$
f(x+\Delta x)-f(x)>0
$$

Tức là khi tăng $x$, hàm số tăng.

Điều này có nghĩa là $x$ đã đi qua vùng tối ưu và đang nằm về phía bên phải.

Trường hợp 3: $L=R$
$$
f(x+\Delta x)-f(x)=0
$$

Số lượng phần tử ở hai phía bằng nhau, do đó tổng chi phí không thay đổi khi dịch chuyển $x$ trong khoảng tương ứng.

Để hàm số đạt cực tiểu, ta cần tìm vị trí mà:
- Nếu dịch chuyển sang trái, hàm số không giảm.
- Nếu dịch chuyển sang phải, hàm số không giảm.
Nói cách khác, số phần tử ở mỗi phía phải cân bằng, hoặc vị trí $x$ phải nằm giữa hai phần tử sao cho không phía nào chiếm đa số.

Đây chính xác là định nghĩa của trung vị (Median):
- Nếu $n$ lẻ, trung vị là phần tử đứng ở vị trí $\frac{n+1}{2}$.
- Nếu $n$ chẵn, mọi giá trị nằm giữa hai phần tử ở vị trí $\frac n2$ và $\frac n2+1$ đều tối ưu.

Vì vậy:
$$
\boxed{\operatorname*{argmin}_{x} f(x)=\text{Median}(p_1,\ldots,p_n)}
$$

Với $n$ chẵn, tập nghiệm tối ưu là cả đoạn giữa hai trung vị.

**Độ phức tạp:**

- Thời gian: $\mathcal{O}(N\log N)$ do cần sắp xếp mảng và duyệt qua các giá trị.
- Bộ nhớ: $\mathcal{O}(N)$ nếu không tính bộ nhớ được sử dụng bởi thuật toán sắp xếp.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
int p[mxN];

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        cin >> p[i];
    }
    sort(p + 1, p + 1 + n);
    int m = (n + 1) / 2;
    long long ans = 0;
    for (int i = 1; i <= n; ++i)
    {
        ans += abs(p[i] - p[m]);
    }
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