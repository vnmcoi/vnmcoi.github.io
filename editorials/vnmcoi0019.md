Để giải bài toán đếm số lượng giá trị phân biệt trong một dãy số, ta có thể sử dụng nhiều phương pháp. Trong lời giải này, chúng ta sẽ sử dụng kỹ thuật rời rạc hóa (Coordinate Compression) kết hợp với sắp xếp.

## Rời rạc hóa

Rời rạc hóa là kỹ thuật chuyển các giá trị lớn thành các giá trị nhỏ hơn, nhưng vẫn giữ nguyên thứ tự giữa các phần tử.

Ví dụ, với dãy:

$$ [100, 5, 100, 20, 5] $$

Sau khi sắp xếp và loại bỏ các giá trị trùng nhau, ta thu được:

$$ [5,20,100] $$

Ta có thể ánh xạ các giá trị này thành:

$$ [1,2,3] $$

Việc thay đổi giá trị cụ thể không làm thay đổi tính chất phân biệt của các phần tử. Vì vậy, số lượng giá trị phân biệt trong dãy ban đầu chính là số lượng giá trị khác nhau sau khi rời rạc hóa.

## Thực hiện

Đầu tiên, ta đọc $n$ phần tử của dãy và lưu chúng vào một vector `v`.

Tiếp theo, ta thực hiện:

1. Sắp xếp vector `v` theo thứ tự tăng dần.
2. Sử dụng `unique()` để loại bỏ các phần tử trùng nhau liên tiếp.
3. Sử dụng `erase()` để xóa các phần tử trùng khỏi vector.

Sau khi thực hiện các bước trên, vector `v` chỉ còn chứa những giá trị phân biệt của dãy ban đầu.

Do đó, kết quả cần tìm chính là:

$$ ans = |v| $$

Trong C++, ta có thể lấy số lượng phần tử hiện tại của vector bằng `v.size()`.

Độ phức tạp:

- Thời gian: $\mathcal {O} (n\log n)$, do bước sắp xếp chiếm độ phức tạp lớn nhất.
- Bộ nhớ: $\mathcal {O} (n)$, để lưu các phần tử của dãy trong vector.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 2e5 + 5;

int N;
int x[mxN];

void solve(void)
{
    cin >> N;
    vector<int> v;
    for (int i = 1; i <= N; ++i)
    {
        cin >> x[i];
        v.push_back(x[i]);
    }
    sort(v.begin(), v.end());
    v.erase(unique(v.begin(), v.end()), v.end());
    cout << v.size();
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```