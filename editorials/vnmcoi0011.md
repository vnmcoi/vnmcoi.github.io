Let $f_x$ denote the minimum number of steps to reduce $x$ to $0$.

**Base case:** $f_0 = 0$. Initialize all other states to infinity.

**General case:**

From any state $x$, we can transition into smaller state $x - j$, where $j$ is any digit of $x$. Since each subtraction costs $1$ step, the optimal answer for $x$ relies on the optimal answers of its reachable smaller states.

Iterating $x$ from $1$ to $n$, we extract each digit $j$ of $x$ and update the DP table using the following transition:

$$
f_x = \min_{j \in \text{digits}(x)} (f_{x - j} + 1)
$$

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e6 + 5;

int n;
int f[mxN];

void solve(void)
{
    cin >> n;
    memset(f, 0x3f, sizeof(f));
    f[0] = 0;
    for (int i = 1; i <= n; ++i)
    {
        int x = i;
        while (x != 0)
        {
            int j = x % 10;
            x /= 10;
            f[i] = min(f[i], f[i - j] + 1);
        }
    }
    cout << f[n];
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```