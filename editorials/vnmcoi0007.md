**Dynamic Programming:**
Dynamic Programming solves complex problems by building up answers from smaller subproblems.

Let $f_x$ be the number of ways to construct the sum $x$.

* **Base case:** $f_0 = 1$ (there is exactly one way to make a sum of $0$ by don't roll the dice).

To find $f_x$ for any $x > 0$, consider the value of the last die thrown. The last throw could be any integer $j$ between $1$ and $6$. Before rolling this $j$, our sum must have been $x - j$.

Thus, the total number of ways to reach sum $x$ is the sum of the ways to reach all valid previous states. The state transition equation is:

$$
f_x = \sum_{j = 1}^{6} f_{x - j} \text { (for all $x - j \ge 0$)}
$$

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e6 + 5;
const int MOD = 1e9 + 7;

int n;
int f[mxN];

void solve(void)
{
    cin >> n;
    f[0] = 1;
    for (int i = 1; i <= n; ++i)
    {
        for (int j = 1; j <= 6; ++j)
        {
            if (i - j < 0)
            {
                break;
            }
            f[i] = (f[i] + f[i - j]) % MOD;
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