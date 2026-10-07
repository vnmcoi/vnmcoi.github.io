Since we must process customer queries dynamically in their given order, we cannot sort the querries offline. Instead, we store all ticket prices in a `std::multiset`, which supports $\mathcal {O} (\log N)$ insertions, deletions, and lookups.

For each customer with maximum price $t$, we need to find the largest available ticket $h \le t$. We can achieve this using the `upper_bound` member function, which returns an iterator to the first element strictly greater than $t$.

By checking the position of this iterator:
1. If the iterator is the first element, every available ticket is strictly greater than $t$. The answer is $-1$.
2. Otherwise, we safely decrement the iterator to point to the largest ticket $\le t$.

```cpp
#include <bits/stdc++.h>
using namespace std;

int n, m;
multiset<int> h, t;

void solve(void)
{
    cin >> n >> m;
    for (int i = 1; i <= n; ++i)
    {
        int x;
        cin >> x;
        h.insert(x);
    }
    for (int i = 1; i <= m; ++i)
    {
        int t;
        cin >> t;
        multiset<int>::iterator itr = h.upper_bound(t);
        if (itr == h.begin())
        {
            cout << -1 << '\n';
        }
        else
        {
            --itr;
            cout << *itr << '\n';
            h.erase(itr);
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