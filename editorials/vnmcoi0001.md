To solve this problem, we can use a `while` or `for` loop to simulate the changes to $n$ step-by-step until it reaches 1.

```cpp
#include <bits/stdc++.h>
using namespace std;

long long n;

void solve(void)
{
    cin >> n;
    while (n != 1)
    {
        cout << n << ' ';
        if (n % 2 == 0)
        {
            n /= 2;
        }
        else
        {
            n = n * 3 + 1;
        }
    }
    cout << n;
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```