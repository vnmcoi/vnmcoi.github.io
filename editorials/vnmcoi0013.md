Để sinh tất cả các hoán vị khác nhau của một xâu, ta có thể sử dụng thuật toán quay lui hoặc thuật toán sinh hoán vị.

Trong C++, hàm `next_permutation()` cho phép sinh hoán vị tiếp theo theo thứ tự từ điển. Vì vậy, ta có thể sử dụng hàm này để liệt kê tất cả các xâu khác nhau được tạo từ các ký tự của xâu ban đầu.

## Đếm số lượng hoán vị khác nhau

Nếu tất cả các ký tự trong xâu đều khác nhau, số hoán vị được tạo ra là:

$$ n! $$

Tuy nhiên, nếu xâu có các ký tự trùng nhau, một số hoán vị sẽ tạo ra cùng một xâu. Khi đó, số lượng hoán vị khác nhau được tính bằng công thức hoán vị lặp:

$$ \frac{n!}{a_1! \times a_2! \times \cdots \times a_m!} $$

Trong đó:

- $n$ là độ dài của xâu.
- $m$ là số ký tự phân biệt trong xâu.
- $a_i$ là số lần xuất hiện của ký tự thứ $i$.

## Sinh các hoán vị

Đầu tiên, ta sắp xếp xâu theo thứ tự từ điển tăng dần. Khi đó, xâu ban đầu chính là hoán vị nhỏ nhất.

Tiếp theo, sử dụng `next_permutation()` để sinh lần lượt các hoán vị tiếp theo. Mỗi lần hàm trả về `true`, ta lưu hoán vị vừa sinh vào danh sách.

Quá trình kết thúc khi không còn hoán vị nào lớn hơn hoán vị hiện tại.

Cuối cùng, in ra số lượng hoán vị đã sinh được, sau đó in toàn bộ danh sách. Do các hoán vị được sinh theo thứ tự từ điển, kết quả cũng sẽ được in theo thứ tự từ điển tăng dần.

Độ phức tạp:

Gọi $k$ là số lượng hoán vị khác nhau của xâu.

- Thời gian: $\mathcal{O} (k \cdot n)$ để sinh và lưu các hoán vị, chưa tính chi phí sắp xếp ban đầu $\mathcal{O} (n\log n)$.
- Bộ nhớ: $\mathcal{O} (k \cdot n)$ để lưu toàn bộ các hoán vị.

```cpp
#include <bits/stdc++.h>
using namespace std;

string S;

void solve(void)
{
    cin >> S;
    sort(S.begin(), S.end());
    vector<string> v;
    v.push_back(S);
    while (next_permutation(S.begin(), S.end()) == true)
    {
        v.push_back(S);
    }
    cout << v.size() << '\n';
    for (const string &s : v)
    {
        cout << s << '\n';
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