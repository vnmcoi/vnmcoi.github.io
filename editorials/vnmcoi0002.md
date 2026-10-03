There are multiple ways to solve this, but we will use a standard frequency array approach. For every number $x$ in the input, we mark `found[x] = 1`. Afterward, we just iterate from $1$ to $n$ to find the only number that is still marked as $0$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
int found[mxN];

void solve(void)
{
    cin >> n;
    for (int i = 1; i < n; ++i)
    {
        int x;
        cin >> x;
        found[x] = 1;
    }
    for (int i = 1; i <= n; ++i)
    {
        if (found[i] == 0)
        {
            cout << i;
        }
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