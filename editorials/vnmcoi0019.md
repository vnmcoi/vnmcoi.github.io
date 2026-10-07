**Brute-Force:**

Linearly iterate through the subarray $[a, b]$ for each of the $Q$ queries.

*Time complexity:* $\mathcal {O}(N \times Q)$, which is too slow.

**Prefix Sum:**

We can optimize the range queries to $\mathcal {O}(1)$ time using a Prefix Sum array. We define an array `pref` where `pref[i]` stores the sum of the elements from index $1$ to $i$.

The sum of the value in the range $[a, b]$ can be mathematically derived by taking the prefix sum up to $b$ and subtracting the prefix sum up to $a - 1$:

$$
\text {Sum}(a, b) = \text {pref}[b] - \text {pref}[a - 1]
$$

*Time complexity:* $\mathcal {O}(N + Q)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n, q;
int x[mxN];
long long pref[mxN];

void solve(void)
{
    cin >> n >> q;
    for (int i = 1; i <= n; ++i)
    {
        cin >> x[i];
        pref[i] = pref[i - 1] + x[i];
    }
    while (q--)
    {
        int a, b;
        cin >> a >> b;
        cout << pref[b] - pref[a - 1] << '\n';
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