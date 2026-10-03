**Constructive approach:** Constructive problems require us to build an output that satisfies certain conditions in this case arranging integers $1$ to $n$ such that no adjacent elements have an absolute difference of $1$.

Solutions to constructive problems typically revolve around observing and leveraging a specific parity pattern.

*(Try to solve it yourself before checking the solution below!)*

```cpp
#include <bits/stdc++.h>
using namespace std;

int n;

void solve(void)
{
    cin >> n;
    if (n == 1)
    {
        cout << 1;
    }
    else if (n == 2 || n == 3)
    {
        cout << "NO SOLUTION";
    }
    else
    {
        if (n % 2 == 0)
        {
            for (int i = n - 1; i >= 1; i -= 2)
            {
                cout << i << ' ';
            }
            for (int i = n; i >= 2; i -= 2)
            {
                cout << i << ' ';
            }
        }
        else
        {
            for (int i = n; i >= 1; i -= 2)
            {
                cout << i << ' ';
            }
            for (int i = n - 1; i >= 2; i -= 2)
            {
                cout << i << ' ';
            }
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