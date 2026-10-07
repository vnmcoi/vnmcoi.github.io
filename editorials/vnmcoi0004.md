**Greedy approach:** To satisfy the condition optimally, each element $x_i$ must be raised to match the maximum value of the prefix $x_1, x_2, \ldots, x_i$.

Thus, we can iterate through the array while maintaining a running maximum, $mx$. The total minimum moves will the the sum of $(mx - x_i)$ for all $1 \le i \le n$ (since each move increases a value by exactly $1$).

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
int x[mxN];

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        cin >> x[i];
    }
    int mx = 0;
    long long ans = 0;
    for (int i = 1; i <= n; ++i)
    {
        mx = max(mx, x[i]);
        ans += mx - x[i];
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