**Ad-hoc / Math approach:** Ad-hoc problems often rely on pattern recognition rather than standard algorithm. For this spiral, we can observe that the maximum value in any "layer" (defined by $mx = \max(y, x)$) is exacly $mx^2$.

By checking if $mx$ is even or odd, we know which corner the $mx^2$ value sits in. From there, we can mathematically substract the distance to our target coordinates $(y, x)$ to find the answer in $\mathcal{O} (1)$ time.

```cpp
#include <bits/stdc++.h>
using namespace std;

int t;

long long solve(int y, int x)
{
    int mx = max(y, x);
    long long ans = 1LL * mx * mx;
    if (mx == y)
    {
        if (y % 2 == 0)
        {
            return ans - (x - 1);
        }
        else
        {
            return ans - (y - 1) - (y - x);
        }
    }
    else
    {
        if (x % 2 == 0)
        {
            return ans - (x - 1) - (x - y);
        }
        else
        {
            return ans - (y - 1);
        }
    }
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    cin >> t;
    for (int i = 1; i <= t; ++i)
    {
        int y, x;
        cin >> y >> x;
        cout << solve(y, x) << '\n';
    }
    return 0;
}
```