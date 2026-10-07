**Sweep Line Algorithm:**

Because the coordinates can be up to $10^9$, creating a frequency array for every second will resulf in a TLE error. Instead, we can process this using a Sweep Line approach.

Each customer's visit $[a, b]$ can be broken down into two discrete events:
* An arrival event at time $a$: `(a, +1)`.
* A departure event at time $b$: `(b + 1, -1)`.

We store all $2N$ events in a `std::vector` and sort them by time. By iterating through the sorted vector and keeping a prefix sum of the second elements, we effectively track the number of custormers in the restaurant at any valid timestamp.

```cpp
#include <bits/stdc++.h>
using namespace std;

int n;
vector<pair<int, int>> v;

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        int a, b;
        cin >> a >> b;
        v.push_back(make_pair(a, 1));
        v.push_back(make_pair(b + 1, -1));
    }
    sort(v.begin(), v.end());
    int ans = 0;
    int cur = 0;
    for (const pair<int, int> &curr : v)
    {
        cur += curr.second;
        ans = max(ans, cur);
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