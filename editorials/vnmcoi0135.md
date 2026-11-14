Để giải quyết bài toán này, chúng ta cần vận dụng tính chất cơ bản của số nguyên tố.

Gọi $n$ là số nguyên cần kiểm tra.

Theo định nghĩa, một số nguyên tố là số nguyên dương lớn hơn $1$ và chỉ có đúng hai ước dương là $1$ và chính nó. Ngược lại, một số nguyên lớn hơn $1$ có nhiều hơn hai ước dương được gọi là hợp số.

**Ý tưởng cơ bản**

Giả sử $n$ là hợp số. Khi đó, chúng ta có thể biểu diễn $n$ dưới dạng tích của hai số nguyên $a$ và $b$ sao cho:

$$
a \times b = n
$$

Xét trường hợp $a \le b$, ta có:

$$
a^2 \le a \times b = n
$$

Suy ra:

$$
a \le \sqrt{n}
$$

Như vậy, nếu $n$ là hợp số thì chắc chắn tồn tại ít nhất một ước của $n$ nằm trong đoạn $[2;\sqrt{n}]$.

Do đó, để kiểm tra tính nguyên tố của $n$, chúng ta chỉ cần duyệt tuần tự các số nguyên từ $2$ đến $\sqrt{n}$ và kiểm tra xem có số nào chia hết $n$ hay không.

- Nếu tồn tại ít nhất một ước trong đoạn này, $n$ là hợp số.
- Nếu không tồn tại ước nào, $n$ là số nguyên tố.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(\sqrt{N})$, với $N$ là giá trị của số cần kiểm tra.
- Bộ nhớ: $\mathcal{O}(1)$.

**Cải tiến bằng kỹ thuật nhảy bước**

Quan sát hai số nguyên tố đầu tiên là $2$ và $3$.

Ta nhận thấy mọi số nguyên lớn hơn $3$ đều có thể biểu diễn dưới một trong sáu dạng:

$$
6k,\ 6k+1,\ 6k+2,\ 6k+3,\ 6k+4,\ 6k+5
$$

Trong đó:

- $6k$ và $6k+2$ là các số chẵn nên chia hết cho $2$.
- $6k+3$ chia hết cho $3$.
- $6k+4$ là số chẵn nên chia hết cho $2$.

Vì vậy, nếu một số nguyên tố lớn hơn $3$ thì nó chỉ có thể thuộc một trong hai dạng:

$$
6k+1
$$

hoặc

$$
6k+5
$$

Tương đương với:

$$
6k-1 \quad \text{hoặc} \quad 6k+1
$$

**Lưu ý:** Đây là điều kiện cần, không phải điều kiện đủ. Một số có dạng $6k\pm1$ chưa chắc là số nguyên tố. Ví dụ, $25=6\times4+1$ nhưng vẫn là hợp số.

Từ nhận xét trên, chúng ta có thể cải tiến thuật toán như sau:

- Xử lý riêng hai trường hợp $n=2$ và $n=3$, vì đây là hai số nguyên tố.
- Nếu $n\le1$, $n$ chia hết cho $2$ hoặc chia hết cho $3$, thì $n$ không phải số nguyên tố.
- Sau đó, chỉ cần kiểm tra các ước có dạng $6k-1$ và $6k+1$ từ $5$ đến $\sqrt n$.

Cụ thể, ta bắt đầu với $k=5$ và tăng thêm $6$ sau mỗi lần lặp. Ở mỗi bước, kiểm tra đồng thời hai giá trị $k$ và $k+2$.

Nếu một trong hai giá trị chia hết $n$, ta kết luận $n$ là hợp số. Ngược lại, nếu duyệt hết mà không tìm thấy ước nào, $n$ là số nguyên tố.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(\sqrt{N})$. Kỹ thuật nhảy bước giúp giảm đáng kể số lần kiểm tra so với cách duyệt tuần tự thông thường.
- Bộ nhớ: $\mathcal{O}(1)$.

```cpp
#include <bits/stdc++.h>
using namespace std;

long long N;

bool check(long long N)
{
    if (N == 2 || N == 3)
    {
        return true;
    }
    if (N <= 1 || N % 2 == 0 || N % 3 == 0)
    {
        return false;
    }
    for (int k = 5; 1LL * k * k <= N; k += 6)
    {
        if (N % k == 0 || N % (k + 2) == 0)
        {
            return false;
        }
    }
    return true;
}

void solve(void)
{
    cin >> N;
    if (check(N) == true)
    {
        cout << "YES";
    }
    else
    {
        cout << "NO";
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