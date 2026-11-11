Vì $ n \le 20$, ta có thể sử dụng đệ quy vét cạn để thử tất cả các cách chia $n$ quả táo thành hai nhóm.

Với mỗi quả táo, ta có hai lựa chọn:
- Đưa quả táo vào nhóm thứ nhất.
- Đưa quả táo vào nhóm thứ hai.

Do đó, có tổng cộng $2^n$ cách phân chia.

Ta sử hàm đệ quy `wayslui(n, s1, s2)`, trong đó:
- $n$ là vị trí quả táo đang xét.
- $s_1$ là tổng trọng lượng của nhóm đầu tiên.
- $s_2$ là tổng trọng lượng của nhóm thứ hai.

Ở mỗi bước đệ quy, ta lần lượt thử đưa quả táo hiện tại vào nhóm đầu tiên rồi nhóm thứ hai và tiếp tục xét những quả táo tiếp theo.

Khi đã xét hết $n$ quả táo thì ta thực hiện kiểm tra kết quả.

Độ phức tạp:
- Thời gian: $\mathcal {O} (2^n)$, vì mỗi quả táo có hai lựa chọn phân nhóm.
- Bộ nhớ: $\mathcal {O} (n)$, do độ sâu tối đa của đệ quy là $n$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 20 + 5;

int N;
int p[mxN];
long long ans = 1e18;

void wayslui(int n, long long s1, long long s2)
{
    if (n == N + 1)
    {
        ans = min(ans, abs(s1 - s2));
        return;
    }
    wayslui(n + 1, s1 + p[n], s2);
    wayslui(n + 1, s1, s2 + p[n]);
}

void solve(void)
{
    cin >> N;
    for (int i = 1; i <= N; ++i)
    {
        cin >> p[i];
    }
    wayslui(1, 0, 0);
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