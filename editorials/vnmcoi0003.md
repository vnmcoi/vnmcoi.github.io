**Brute-force approach:** Iterate through every starting position $i$ $(1 \le i \le |s|)$ and use a nested loop with pointer $j$ to find the longest block of identical characters. The answer is the maximum $j - i + 1$ found.

**Time complexity:** $\mathcal{O} (N^2)$.

**Two pointers approach:** We can skip the redundant checks to optimize the time complexity. Consider the string `AAAAB`. If we start at $i = 1$, the identical block ends at $j = 4$. If we advance $i$ to $i = 2$, the maximum length ending at $j$ will only decrease since $(j - i > j - (i + 1))$.

Therefore, it is always optimal to jump directly to $j + 1$ (the start of the next different character block). We can maintain a pointer $j$ that only scans forward, updating our answer for each contiguous block of identical characters.

**Time complexity:** $\mathcal{O} (N)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

string s;

void solve(void)
{
    cin >> s;
    int n = s.length();
    s = ' ' + s;
    int j = 1;
    int ans = 0;
    for (int i = 1; i <= n; ++i)
    {
        while (j <= n && s[i] == s[j])
        {
            ++j;
        }
        ans = max(ans, j - i);
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