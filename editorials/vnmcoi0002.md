Để giải bài toán này, ta sử dụng vòng lặp while để mô phỏng quá trình biến đổi của $n$. Ở mỗi bước, nếu $n$ là số chẵn, ta chia $n$ cho $2$; ngược lại, ta nhân $n$ với $3$ rồi cộng $1$. Quá trình tiếp tục cho đến khi $n = 1$. Ta in giá trị của $n$ tại mỗi bước để thu được dãy số theo yêu cầu.

```cpp
#include <bits/stdc++.h>
using namespace std;

long long N;

void solve(void)
{
    cin >> N;
    while (N != 1)
    {
        cout << N << ' ';
        if (N % 2 == 0)
        {
            N /= 2;
        }
        else
        {
            N = N * 3 + 1;
        }
    }
    cout << N;
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```