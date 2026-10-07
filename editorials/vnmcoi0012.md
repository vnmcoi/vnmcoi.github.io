Let $f_{i, j}$ denote the number of paths from $(1, 1)$ to $(i, j)$.

**Base case:** $f_{1, 1} = 1$ (assuming $(1, 1)$ is not a trap). Initially all other states to $0$.

**General case:**

Rather than pulling transitions from previous states (Backward DP), we can implement a "Forward DP" (Push DP). For every cell $(i, j)$ we visit, we push its current number of paths forward to its reachable neighbors.

From $(i, j)$, the valid moves are down to $(i + 1, j)$ and right to $(i, j + 1)$. If a target cell is within bounds and is not a trap (*`valid` is true*), we add $f_{i, j}$ to it:

$$f_{i + 1, j} = (f_{i + 1, j} + f_{i, j}) \pmod{10^9 + 7}$$
$$f_{i, j + 1} = (f_{i, j + 1} + f_{i, j}) \pmod{10^9 + 7}$$

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e3 + 5;
const int MOD = 1e9 + 7;

int n;
int f[mxN][mxN];
bool valid[mxN][mxN];

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        string s;
        cin >> s;
        for (int j = 0; j < n; ++j)
        {
            if (s[j] == '.')
            {
                valid[i][j + 1] = true;
            }
        }
    }
    if (valid[1][1] == true)
    {
        f[1][1] = 1;
    }
    for (int i = 1; i <= n; ++i)
    {
        for (int j = 1; j <= n; ++j)
        {
            if (i + 1 <= n && valid[i + 1][j] == true)
            {
                f[i + 1][j] = (f[i + 1][j] + f[i][j]) % MOD;
            }
            if (j + 1 <= n && valid[i][j + 1] == true)
            {
                f[i][j + 1] = (f[i][j + 1] + f[i][j]) % MOD;
            }
        }
    }
    cout << f[n][n];
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```