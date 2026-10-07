**Brute-Force:**

Linearly iterate through the $[a, b]$ for each query;

*Time complexity:* $\mathcal {O}(N \times Q)$, which results in a TLE error.

**Sparse Table (RMQ):**

Because the minimum operation lacks an inverse (subtraction), a Prefix Sum array cannot be used. However, because the minimum operation is idempotent (overlapping ranges do not alter the result), we can use a Sparse Table.

A Sparse Table pre-computes the minimum for all invervals of length $2^k$ in $\mathcal {O}(N \log N)$ time. `v[k][i]` stores the minimum value in the range $[i, i + 2^k - 1]$.

For any query $[a, b]$, let $k = \lfloor \log_2(b - a + 1) \rfloor$. We can retrieve this in $\mathcal {O}(1)$ time using `31 - __builtin_clz(b - a + 1)`. We then cover the query range with two lapping intervals of length $2^k$: one anchored at the left boundary $a$, and one anchored at the right boundary $b$.

The minimum of the range is:

$$
\min(\text {Table}[k][a], \text {Table}[k][b - 2^k + 1])
$$

*Time complexity:* $\mathcal {O}(N \log N)$ to build, $\mathcal {O}(1)$ per query. Overall $\mathcal {O}(N \log N + Q)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

#define MASK(x) (1LL << (x))

const int mxN = 2e5 + 5;
const int LOG = 18;

int n, q;
int x[mxN];
int v[LOG + 1][mxN];

int get(int a, int b)
{
    int k = 31 - __builtin_clz(b - a + 1);
    return min(v[k][a], v[k][b - MASK(k) + 1]);
}

void solve(void)
{
    cin >> n >> q;
    for (int i = 1; i <= n; ++i)
    {
        cin >> x[i];
        v[0][i] = x[i];
    }
    for (int j = 1; j <= LOG; ++j)
    {
        for (int i = 1; i <= n - MASK(j) + 1; ++i)
        {
            v[j][i] = min(v[j - 1][i], v[j - 1][i + MASK(j - 1)]);
        }
    }
    while (q--)
    {
        int a, b;
        cin >> a >> b;
        cout << get(a, b) << '\n';
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