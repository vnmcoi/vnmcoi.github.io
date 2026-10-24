## 1. Tham lam

Ta cần biến đổi mảng thành một mảng không giảm, tức là $x_i \ge x\_{i-1}$ với mọi $i \ge 2$, bằng cách tăng giá trị các phần tử. Để đạt được số bước tối thiểu, tại mỗi vị trí $i$, ta chỉ tăng $x_i$ khi giá trị của nó nhỏ hơn giá trị lớn nhất đã gặp trước đó.

Ví dụ với mảng:

```
5
3 2 5 1 7
```

- Vị trí $1$: $x_1 = 3$. Vì chưa có phần tử nào đứng trước nên ta giữ nguyên giá trị $3$.
- Vị trí $2$: $x_2 = 2 < 3$. Ta cần tăng $x_2$ lên $3$, tốn $3 - 2 = 1$ bước.
- Vị trí $3$: $x_3 = 5 \ge 3$. Ta giữ nguyên giá trị $5$.
- Vị trí $4$: $x_4 = 1 < 5$. Ta cần tăng $x_4$ lên $5$, tốn $5 - 1 = 4$ bước.
- Vị trí $5$: $x_5 = 7 \ge 5$. Ta giữ nguyên giá trị $7$.

Tổng số bước tối thiểu là $1 + 4 = 5$.

## 2. Tối ưu thuật toán duyệt

Một cách tiếp cận trực tiếp là tại mỗi vị trí $i$, duyệt lại các phần tử đứng trước để tìm giá trị lớn nhất. Tuy nhiên, cách này có độ phức tạp thời gian $O(n^2)$, không phù hợp với giới hạn $n \le 2 \cdot 10^5$.

Thay vào đó, ta sử dụng biến `mx` để lưu giá trị lớn nhất đã gặp trong quá trình duyệt mảng. Với mỗi phần tử $x_i$:

- Cập nhật `mx = max(mx, x[i])`.
- Cộng `mx - x[i]` vào đáp án. Đây chính là số bước cần thiết để tăng phần tử hiện tại lên giá trị phù hợp.

Vì mỗi phần tử chỉ được duyệt một lần, thuật toán có độ phức tạp thời gian $O(n)$ và độ phức tạp bộ nhớ phụ $O(1)$ nếu không tính bộ nhớ lưu mảng.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int N;
int X[mxN];

void solve(void)
{
    cin >> N;
    for (int i = 1; i <= N; ++i)
    {
        cin >> X[i];
    }
    long long ans = 0;
    int mx = 0;
    for (int i = 1; i <= N; ++i)
    {
        mx = max(mx, X[i]);
        ans += mx - X[i];
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