## Phân tích ban đầu

Ta thấy rằng để có thể phân phòng một cách tối ưu cho các yêu cầu và với phòng hiện tại thì chúng ta sẽ tìm kiếm phòng với diện tích nhỏ nhất có thể nhưng vẫn nằm trong giới hạn của yêu cầu là $[a_i - k; a_i + k]$.

## Chiến thuật tham lam

Ví dụ: Gọi lần lượt hai yêu cầu là $a_1, a_2, a_1 < a_2$. Ta xét một phòng $b_i$ nhỏ nhất thỏa mãn $b_i \in [a_1 - k; a_1 + k]$.

Ta sẽ thấy rằng nếu $b_i \notin [a_2 - k; a_2 + k]$ thì $b_i$ đã chính là phòng nên được phân cho $a_1$ để các phòng $b_j > b_i$ có tỉ lệ cao hơn được phân cho $a_2$.

Ngược lại, nếu $b_i \in [a_2 - k; a_2 + k]$ ta vẫn phân $b_i$ về $a_1$ vì các phòng lớn hơn sẽ có tỉ lệ lớn hơn phân được cho $a_2$ nếu phân cho $a_2$ thì $a_1$ bị mất đi phòng nhỏ nhất hợp lệ suy ra không chắc sẽ có khả năng ghép lại với phòng mới lớn hơn.

## Tối ưu hóa bài toán

Để tìm kiếm được phòng nhỏ nhất theo yêu cầu thì vì trong bài toán này có sự ảnh hưởng của việc một phòng không thể nào được dùng lại nên việc tìm kiếm nhị phân là bất khả thi.

Thay vì vậy chúng ta sử dụng kĩ thuật hai con trỏ để tối ưu hóa tốc độ duyệt.

Gọi $i, j$ lần lượt là vị trí của con trỏ trên dãy $a$ và dãy $b$.

Ta thấy rằng sẽ có các trường hợp:
- $|a_i - b_j| \le k$: Phòng $b_j$ là phòng nhỏ nhất hợp lệ ta phân phòng $b_j$ cho yêu cầu $a_i$.
- $a_i - b_j < k$: Yêu cầu $a_i$ hiện tại quá bé so với phòng đang xét là $b_j$ nên ta chuyển lên yêu cầu lớn hơn.
- $a_i - b_j > k$: Phòng $b_j$ hiện tại quá bé so với yêu cầu đang xét là $a_i$ nên ta chuyển lên phòng lớn hơn.

## Độ phức tạp thời gian

Sắp xếp: $\mathcal {O} (N \log N)$.
Hai con trỏ: $\mathcal {O} (N)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int N, M, K;
int A[mxN];
int B[mxN];

void solve(void)
{
    cin >> N >> M >> K;
    for (int i = 1; i <= N; ++i)
    {
        cin >> A[i];
    }
    for (int i = 1; i <= M; ++i)
    {
        cin >> B[i];
    }
    sort(A + 1, A + 1 + N);
    sort(B + 1, B + 1 + M);
    int i = 1;
    int j = 1;
    int ans = 0;
    while (i <= N && j <= M)
    {
        if (abs(A[i] - B[j]) <= K)
        {
            ++i;
            ++j;
            ++ans;
        }
        else if (A[i] - B[j] < K)
        {
            ++i;
        }
        else
        {
            ++j;
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