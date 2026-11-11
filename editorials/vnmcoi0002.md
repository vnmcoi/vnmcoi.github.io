Để giải bài toán này, ta sử dụng vòng lặp while để mô phỏng quá trình biến đổi của $N$. Ở mỗi bước, nếu $N$ là số chẵn, ta chia $N$ cho $2$; ngược lại, ta nhân $N$ với $3$ rồi cộng $1$. Quá trình tiếp tục cho đến khi $N = 1$. Ta in giá trị của $N$ tại mỗi bước để thu được dãy số theo yêu cầu.

**Lưu ý:** Vì ta không biết giá trị của $N$ có thể vượt quá `int` trong mọi bước hay không nên ta buộc phải sử dụng `long long` để tránh trường hợp trào giá trị của biến.

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