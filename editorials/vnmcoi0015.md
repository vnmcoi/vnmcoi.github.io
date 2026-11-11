Để tìm số bị thiếu trong dãy số từ $1$ đến $n$, ta có thể sử dụng nhiều phương pháp khác nhau. Trong bài này, chúng ta sẽ sử dụng mảng đánh dấu để ghi nhận những số đã xuất hiện trong dữ liệu đầu vào.

## Mảng đánh dấu

Ta tạo một mảng `has`, trong đó:

- `has[x] = 1` nếu số $x$ đã xuất hiện.
- `has[x] = 0` nếu số $x$ chưa xuất hiện.

Ban đầu, tất cả các phần tử của mảng `has` đều có giá trị bằng $0$.

Sau đó, ta đọc $n-1$ số từ dữ liệu đầu vào. Với mỗi số $x$, ta đánh dấu `has[x] = 1`.

Vì đề bài cho biết các số đều khác nhau và thuộc đoạn từ $1$ đến $n$, nên chỉ có duy nhất một số chưa được đánh dấu.

## Tìm số bị thiếu

Sau khi đọc dữ liệu, ta duyệt các số từ $1$ đến $n$.

Nếu gặp một số $i$ có `has[i] = 0`, thì $i$ chính là số bị thiếu cần tìm.

Độ phức tạp:

- Thời gian: $\mathcal {O} (n)$, vì ta duyệt qua $n-1$ số đầu vào và tối đa $n$ phần tử của mảng đánh dấu.
- Bộ nhớ: $\mathcal {O} (n)$, để lưu mảng đánh dấu.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int N;
int has[mxN];

void solve(void)
{
    cin >> N;
    for (int i = 1; i < N; ++i)
    {
        int x;
        cin >> x;
        has[x] = 1;
    }
    for (int i = 1; i <= N; ++i)
    {
        if (has[i] == 0)
        {
            cout << i;
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