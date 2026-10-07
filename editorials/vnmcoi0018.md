**Greedy Approach (Interval Scheduling):**

To maximize the number of non-overlapping movies, we must use a greedy strategy: sort all movies by their **ending times** in ascending order.

By always selecting the available movie that ends first, we safely maximize the remaining free time for future movies.

*Common Pitfalls to avoid:*
1. **Sorting by shortest duration:** Fails if a short movie bridges across two longer, non-overlapping movies (e.g, intervals `[1, 5]`, `[4, 6]`, `[5, 9]`).
2. **Sorting by earliest start time:** Fails if a movie starts very early but lasts a very long time, blocking all other times (e.g, `[1, 100]`, `[1, 5]`, `[5, 9]`).

**Algorithm:**

Sort the array of pairs by the ending time. Maintain a varible to track the current time on the timeline. Iteratate through the movies: if a movie start time is before the varible $(\le cur)$, increment the answer and update to the new ending time.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
pair<int, int> v[mxN];

bool compare(const pair<int, int> &a, const pair<int, int> &b)
{
    if (a.second != b.second)
    {
        return a.second < b.second;
    }
    return a.first > b.first;
}

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        cin >> v[i].first >> v[i].second;
    }
    sort(v + 1, v + 1 + n, compare);
    int ans = 0;
    int cur = 0;
    for (int i = 1; i <= n; ++i)
    {
        if (v[i].first >= cur)
        {
            ++ans;
            cur = v[i].second;
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