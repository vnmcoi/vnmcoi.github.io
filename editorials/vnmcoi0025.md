Để giải quyết bài toán này, chúng ta cần tìm ước chung lớn nhất (GCD) lớn nhất của một cặp số bất kỳ trong mảng.

Nhận xét rằng một số nguyên dương $d$ có thể là ước chung lớn nhất của một cặp số khi và chỉ khi có ít nhất hai phần tử trong mảng chia hết cho $d$.

Gọi `cnt[i]` là số lần xuất hiện của số $i$ trong mảng.

Khi đó, với mỗi giá trị $d$, ta cần đếm số phần tử trong mảng chia hết cho $d$. Nếu số lượng này lớn hơn hoặc bằng $2$, nghĩa là tồn tại ít nhất hai phần tử có ước chung là $d$.

Ta có thể sử dụng kỹ thuật sàng cải tiến từ sàng Eratoshthenes để duyệt qua tất cả các bội của từng số $d$. Cụ thể, với mỗi $d$, duyệt các giá trị $d, 2d, 3d, \ldots$ và cộng số lần xuất hiện của chúng vào biến đếm.

Để tìm đáp án lớn nhất, ta duyệt $d$ theo thứ tự giảm dần từ $10^6$ xuống $1$. Ngay khi tìm được giá trị $d$ có ít nhất hai phần tử chia hết cho nó, ta có thể kết luận đây chính là đáp án và kết thúc duyệt.

Với $M = 10^6$, tổng số phép duyệt các bội của từng giá trị có độ phức tạp: $\mathcal{O}\left(M \log M\right)$.

Bộ nhớ sử dụng là $\mathcal{O}(M)$ để lưu tần suất xuất hiện của các phần tử.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxX = 1e6;

int n;
int cnt[mxX + 5];

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        int x;
        cin >> x;
        ++cnt[x];
    }
    for (int i = mxX; i >= 1; --i)
    {
        int sum = 0;
        for (int j = i; j <= mxX; j += i)
        {
            sum += cnt[j];
        }
        if (sum > 1)
        {
            cout << i;
            return;
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