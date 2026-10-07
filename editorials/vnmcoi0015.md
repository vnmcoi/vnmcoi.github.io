**Greedy + Two Pointers approach:** To minimize the number of gondolas, we must maximize the number of paired children. We can achieve this optimally by pairing the heaviest remaining child with the lightest remaining child.

We sort the array $p$ in ascending order and initialize two pointers: $i = 1$ (lightest possible child) and $j = n$ (heaviest possible child).

At each step, we evaluate the sum of their weights, $p_i + p_j$:
1. If $p_i + p_j \le x$: The pair is valie. We use one gondola and advance both pointers.
2. If $p_i + p_j > x$: The child $p_j$ is too heavy to pair with even the lightest available children. Because the array is sorted, $p_j$ cannot pair with anyone. Thus, $p_j$ must take a gondola alone.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n, x;
int p[mxN];

void solve(void)
{
    cin >> n >> x;
    for (int i = 1; i <= n; ++i)
    {
        cin >> p[i];
    }
    sort(p + 1, p + 1 + n);
    int ans = 0;
    int i = 1;
    int j = n;
    while (i <= j)
    {
        if (i == j)
        {
            ++ans;
            break;
        }
        else if (p[i] + p[j] <= x)
        {
            ++ans;
            ++i;
            --j;
        }
        else
        {
            ++ans;
            --j;
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