## 1. Phân tích bài toán

Việc tính trực tiếp $n!$ với $n$ có thể lên đến $10^9$ là không khả thi, vì kết quả sẽ có số lượng chữ số cực kỳ lớn. Tuy nhiên, bài toán không yêu cầu tính giá trị của $n!$, mà chỉ yêu cầu đếm số chữ số $0$ liên tiếp ở cuối kết quả.

Ta có:

$$ n! = 1 \times 2 \times 3 \times \cdots \times n $$

Một chữ số $0$ ở cuối số nguyên được tạo ra khi tích có một thừa số $10 = 2 \times 5$. Vì vậy, số chữ số $0$ tận cùng của $n!$ bằng số cặp thừa số $2$ và $5$ có thể ghép thành $10$.

Trong tích $n!$, số thừa số $2$ luôn nhiều hơn số thừa số $5$. Do đó, số chữ số $0$ tận cùng chỉ phụ thuộc vào số lượng thừa số $5$.

## 2. Đếm số thừa số $5$

Mỗi số chia hết cho $5$ đóng góp ít nhất một thừa số $5$ vào $n!$. Tuy nhiên, các số là lũy thừa của $5$ còn đóng góp thêm thừa số $5$.

Ví dụ, với $n = 20$, các bội số của $5$ không vượt quá $20$ là $5, 10, 15, 20$. Mỗi số đóng góp một thừa số $5$, nên:

$$ \left\lfloor \frac{20}{5} \right\rfloor = 4 $$

Với $n = 25$, ngoài các bội số của $5$, số $25 = 5^2$ còn đóng góp thêm một thừa số $5$. Vì vậy:

$$ \left\lfloor \frac{25}{5} \right\rfloor + \left\lfloor \frac{25}{25} \right\rfloor = 5 + 1 = 6 $$

Tổng quát, số chữ số $0$ tận cùng của $n!$ được tính bằng công thức:

$$ \boxed{ \left\lfloor \frac{n}{5} \right\rfloor + \left\lfloor \frac{n}{5^2} \right\rfloor + \left\lfloor \frac{n}{5^3} \right\rfloor +\cdots } $$

Ta chỉ cần duyệt các lũy thừa $5^k$ không vượt quá $n$, cộng $\lfloor n/5^k \rfloor$ vào đáp án ở mỗi bước. Khi $5^k > n$, ta dừng thuật toán.

```cpp
#include <bits/stdc++.h>
using namespace std;

int N;

void solve(void)
{
    cin >> N;
    int ans = 0;
    for (int i = 5; i <= N; i *= 5)
    {
        ans += N / i;
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