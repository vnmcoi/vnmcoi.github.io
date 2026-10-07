**Brute-Force:** Linearly search all $m$ apartments for every applicant.

*Time complexity:* $\mathcal {O}(N \times M)$.

**Greedy + Two Pointers:**

*Greedy strategy:* Assign the smallest valid apartment to the smallest applicant. This preserves larger apartments for future applicants who strictly require them.

We start by sorting both the applicants array $A$ and the apartments array $B$ in ascending order. Then, we use two pointers, $i$ and $j$, to traverse $A$ and $B$ simultaneously in $\mathcal {O}(N + M)$ time.

At each step, we evaluate the difference between $a_i$ and $b_j$:
1. If $|a_i - b_j| \le k$: We found a valid match. Increment both $i$ and $j$.
2. If $a_i - b_j > k$: The current apartment is too small for $a_i$. Since $A$ is sorted, it is too small for all subsequent applicants. Increment $j$.
3. If $a_i - b_j < k$: The current apartment is too large for $a_i$. Since $B$ is sorted, all subsequent apartments will also be too large. Increment $i$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;
const int mxM = 2e5 + 5;

int n, m, k;
int a[mxN], b[mxM];

void solve(void)
{
    cin >> n >> m >> k;
    for (int i = 1; i <= n; ++i)
    {
        cin >> a[i];
    }
    for (int i = 1; i <= m; ++i)
    {
        cin >> b[i];
    }
    sort(a + 1, a + 1 + n);
    sort(b + 1, b + 1 + m);
    int i = 1;
    int j = 1;
    int ans = 0;
    while (i <= n && j <= m)
    {
        if (abs(a[i] - b[j]) <= k)
        {
            ++ans;
            ++i;
            ++j;
        }
        else if (a[i] - b[j] > k)
        {
            ++j;
        }
        else
        {
            ++i;
        }
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