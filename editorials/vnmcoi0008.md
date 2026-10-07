Let $f_x$ denote the minimum number of coins required to make a sum of $x$. Since coins can be used an unlimited number of times, this is a variation of the classic Unbounded Knapsack problem.

**Base case:** $f_0 = 0$ (zero coins are needed to make a sum of $0$). All other states are initially set to infinity.

**General case:**
To compute $f_x$, we iterate through every available coin $c_j$. If we choose $c_j$ as the final coin in our sum, the previous state was $x - c_j$.

Thus, the state transition equation is:

$$
f_x = \min_{j = 1}^{n} (f_{x - c_j} + 1) \text { $(x - c_j \ge 0)$}
$$

If $f_x$ remains infinity at the end, it means the sum cannot be formed, so we output $-1$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e2 + 5;
const int mxX = 1e6 + 5;
const int INF = 0x3f3f3f3f;

int n, x;
int c[mxN];
int f[mxX];

void solve(void)
{
    cin >> n >> x;
    for (int i = 1; i <= n; ++i)
    {
        cin >> c[i];
    }
    memset(f, 0x3f, sizeof(f));
    f[0] = 0;
    for (int i = 1; i <= x; ++i)
    {
        for (int j = 1; j <= n; ++j)
        {
            if (i - c[j] >= 0)
            {
                f[i] = min(f[i], f[i - c[j]] + 1);
            }
        }
    }
    if (f[x] == INF)
    {
        cout << -1;
    }
    else
    {
        cout << f[x];
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