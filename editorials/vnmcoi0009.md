Let $f_x$ be the number of ways to create the sum $x$ (remember that each coin can be used an unlimited number of times).

**Base case:** $f_0 = 1$ (there is exactly one way to create a sum of $0$, which is by using $0$ coins).

**General case:**

To find the number of ways to form a sum $x$, we consider the very last coin added to the sum. If we choose to use coin $c_j$ as the final coin, the sum right before adding it must have been $x - c_j$.

Therefore, the total number of ways to create sum $x$ is the sum of the ways to reach all valid previous states using any of our $n$ coins. The transition formula is:

$$
f_x = \sum_{j = 1}^{n} f_{x - c_j} \text { $(x - c_j \ge 0)$}
$$

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e2 + 5;
const int mxX = 1e6 + 5;
const int MOD = 1e9 + 7;

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
    f[0] = 1;
    for (int i = 1; i <= x; ++i)
    {
        for (int j = 1; j <= n; ++j)
        {
            if (i - c[j] >= 0)
            {
                f[i] = (f[i] + f[i - c[j]]) % MOD;
            }
        }
    }
    cout << f[x];
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```