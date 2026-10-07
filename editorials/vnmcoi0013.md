While using a `std::set` is a valid way to filter distinct values, utilizing a `std::vector` alongside the **Sort-Unique-Erase** is a standard, highly efficient C++ technique that run in $\mathcal{O} (N \log {N})$ with minimal overhead.

First, we use `std::sort` to arrange the vector, forcing all identical elements to become adjacent. Next, we apply `std::unique`, which collapsed adjacent duplicates by shifting unique elements to the front. `unique` returns an iterator to the new end of the unique sequence. Finally, we use `v.erase()` to truncate the remaining trailing duplicates.

The number of distinct values is then exactly equal to `v.size()`.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
vector<int> v;

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        int x;
        cin >> x;
        v.push_back(x);
    }
    sort(v.begin(), v.end());
    v.erase(unique(v.begin(), v.end()), v.end());
    cout << v.size();
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```