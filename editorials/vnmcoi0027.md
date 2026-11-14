Đối với bài toán này, chúng ta có thể nhận thấy rằng không có một công thức hay cách giải trực tiếp nào giống với những bài toán đã học. Vì vậy, chúng ta cần quan sát và khai thác tính chất của bài toán để tìm ra hướng giải quyết phù hợp.

Gọi $s$ là số nguyên dương nhỏ nhất mà chúng ta chưa thể tạo được bằng cách chọn một tập con các đồng xu. Khi đó, mọi số nguyên trong đoạn $[0, s-1]$ đều có thể tạo được. Ta gọi tập hợp các tổng có thể tạo được này là $A$.

Để xác định những tổng có thể tạo được, trước tiên chúng ta sắp xếp các đồng xu theo thứ tự tăng dần và lần lượt xét từng đồng xu.

Giả sử hiện tại chúng ta có thể tạo được tất cả các tổng trong đoạn $[0, s-1]$ và đang xét một đồng xu có giá trị $x_i$.

Nếu sử dụng đồng xu này, chúng ta có thể mở rộng tập hợp các tổng có thể tạo được như sau:

- Để tạo tổng $x_i$, chúng ta chỉ cần sử dụng riêng đồng xu này.
- Để tạo tổng $x_i + y$ với $0 \le y \le s-1$, chúng ta sử dụng đồng xu $x_i$ kết hợp với cách tạo tổng $y$ đã biết trước đó.

Như vậy, khi $x_i \le s$, chúng ta có thể tạo được tất cả các tổng trong đoạn $[0, s+x_i-1]$. Do đó, cập nhật $s \leftarrow s+x_i$.

Ngược lại, nếu $x_i > s$, chúng ta không thể tạo được tổng $s$. Thật vậy, do các đồng xu đã được sắp xếp tăng dần nên mọi đồng xu chưa xét đều có giá trị lớn hơn hoặc bằng $x_i$, tức là lớn hơn $s$. Vì vậy, nếu sử dụng bất kỳ đồng xu nào chưa xét, tổng nhận được sẽ vượt quá $s$. Trong khi đó, chỉ sử dụng các đồng xu đã xét thì chúng ta cũng không thể tạo được tổng $s$ theo định nghĩa của $s$.

Vậy $s$ chính là tổng nhỏ nhất không thể tạo được và chúng ta có thể kết thúc thuật toán ngay tại đây.

Ban đầu, ta khởi tạo $s=1$ vì tổng $0$ luôn có thể tạo được bằng cách không chọn đồng xu nào.

Nếu duyệt hết tất cả các đồng xu mà không gặp trường hợp $x_i>s$, đáp án chính là giá trị $s$ hiện tại.

**Độ phức tạp:**

- Thời gian: $\mathcal{O}(N\log N)$ do cần sắp xếp mảng và duyệt qua các đồng xu.
- Bộ nhớ: $\mathcal{O}(N)$ nếu không tính bộ nhớ được sử dụng bởi thuật toán sắp xếp.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int n;
int x[mxN];

void solve(void)
{
    cin >> n;
    for (int i = 1; i <= n; ++i)
    {
        cin >> x[i];
    }
    sort(x + 1, x + 1 + n);
    long long s = 1;
    for (int i = 1; i <= n; ++i)
    {
        if (x[i] > s)
        {
            cout << s;
            return;
        }
        s += x[i];
    }
    cout << s;
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```