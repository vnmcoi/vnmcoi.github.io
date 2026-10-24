**Trường hợp cơ sở:** Với $n = 1$, ta có hai xâu bit có thể tạo thành là $0$ và $1$.

**Hệ thức đệ quy:** Với mỗi $n > 1$, ta có thể tạo ra các xâu bit độ dài $n$ bằng cách thêm $0$ hoặc $1$ vào cuối mỗi xâu bit có độ dài $n - 1$. Vì mỗi xâu bit có thể tạo ra hai xâu mới, số lượng xâu bit độ dài $n$ gấp đôi số lượng xâu bit độ dài $n - 1$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int MOD = 1e9 + 7;

int N;

void solve(void)
{
    cin >> N;
    int ans = 2;
    for (int i = 2; i <= N; ++i)
    {
        ans *= 2;
        ans %= MOD;
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