Let $f_x$ be the number of unique combinations to create the sum $x$ (meaning different permutation of the same coins are counted as exactly $1$ way).

**Base case:** $f_0 = 1$ (there is exactly one way to create a sum of $0$, which is use by using $0$ coins).

**General case:**

The key difference between this problem and *Coin Combination I* is that we must not count different permutations (like $2+2+3$ and $2+3+2$) as separate answers.

By iterating over the coins in the outer loop and updating the DP table for all sums in the inner loop, we ensure that the $j$-th coin is fully processed before the $(j + 1)$-th coin is considered. This make it impossible to add an earlier coin after a later one has been placed. The transition equation remains:

$$
f_i = (f_i + f_{i - c_j}) \pmod{10^9+7} \text { (for all $i \ge c_j$)}
$$

But the loop structure guarantees each combination is generated in a strictly non-decreasing order and counted only once.

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
    for (int j = 1; j <= n; ++j)
    {
        for (int i = c[j]; i <= x; ++i)
        {
            if (f[i - c[j]] != 0)
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