Để giải quyết bài toán này, chúng ta sử dụng thuật toán sàng Eratosthenes.

Ý tưởng chính của thuật toán là: nếu $i$ là một số nguyên tố thì mọi bội số của $i$ lớn hơn $i$ đều là hợp số. Do đó, ta có thể đánh dấu tất cả các bội số này là không phải số nguyên tố.

Cụ thể, ban đầu ta giả sử tất cả các số từ 0 đến n đều là số nguyên tố. Sau đó, ta lần lượt xét các số $i$ từ $2$ đến căn bậc hai của $n$.

Nếu $i$ vẫn được đánh dấu là số nguyên tố, ta tiến hành đánh dấu các bội số của $i$ bắt đầu từ $i * i$ là hợp số. Ta bắt đầu từ $i * i$ vì các bội số nhỏ hơn giá trị này đã được đánh dấu bởi những số nguyên tố nhỏ hơn $i$.

Sau khi hoàn thành quá trình sàng, những số còn được đánh dấu là số nguyên tố chính là các số nguyên tố không vượt quá $n$. Cuối cùng, ta duyệt từ $2$ đến $n$ và in ra các số thỏa mãn.

Lưu ý: Trong cách cài đặt này, chúng ta sử dụng bitset của C++ thay vì các cấu trúc dữ liệu thông thường. bitset lưu trữ các giá trị Boolean dưới dạng bit, nhờ đó giúp tiết kiệm bộ nhớ đáng kể. Ngoài ra, các phép toán trên bit có thể được xử lý hiệu quả, nhưng tốc độ thực tế còn phụ thuộc vào từng trường hợp cụ thể.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(n \log \log n)$.
- Bộ nhớ: $\mathcal{O}(\frac{n}{8})$ byte khi sử dụng bitset.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e7 + 5;

int n;
bitset<mxN> prime;

void eratosthenes(int n)
{
    prime.set();
    prime[0] = prime[1] = false;
    for (int i = 2; i * i <= n; ++i)
    {
        if (prime[i] == true)
        {
            for (int j = i * i; j <= n; j += i)
            {
                prime[j] = false;
            }
        }
    }
}

void solve(void)
{
    cin >> n;
    eratosthenes(n);
    for (int i = 1; i <= n; ++i)
    {
        if (prime[i] == true)
        {
            cout << i << ' ';
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