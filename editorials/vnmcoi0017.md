Bài toán yêu cầu tìm độ dài lớn nhất của một đoạn ký tự liên tiếp mà tất cả ký tự trong đoạn đều giống nhau.

Ta có thể giải bài toán bằng cách duyệt từng vị trí bắt đầu $i$, sau đó tiếp tục duyệt vị trí $j$ cho đến khi gặp ký tự khác với ký tự tại vị trí $i$. Khi đó, độ dài đoạn ký tự giống nhau liên tiếp là:

$$ j-i $$

Ta cập nhật kết quả lớn nhất bằng:

$$ ans=\max(ans,j-i) $$

## Thuật toán trâu

Với mỗi vị trí $i$, ta duyệt $j$ từ $i$ trở đi cho đến khi gặp ký tự khác.

Tuy nhiên, cách làm này có thể phải duyệt lại nhiều ký tự, dẫn đến độ phức tạp thời gian $\mathcal {O} (n^2)$ trong trường hợp xấu nhất.

## Tối ưu bằng kỹ thuật hai con trỏ

Ta có thể tối ưu thuật toán bằng cách sử dụng hai con trỏ $i$ và $j$.

- $i$ là vị trí bắt đầu của đoạn ký tự đang xét.
- $j$ là vị trí đầu tiên có ký tự khác với ký tự tại vị trí $i$.

Khi $j$ đã dừng lại tại ký tự khác, ta biết rằng đoạn từ $i$ đến $j-1$ là đoạn ký tự giống nhau liên tiếp dài nhất bắt đầu tại $i$.

Thay vì tăng $i$ từng vị trí rồi duyệt lại $j$, ta có thể dịch trực tiếp $i$ đến vị trí $j$, vì tất cả các vị trí nằm giữa $i$ và $j-1$ đều đã được xét.

Quá trình này tiếp tục cho đến khi $i$ vượt quá độ dài của xâu.

## Độ phức tạp

- Thời gian: $\mathcal {O} (n)$, vì mỗi con trỏ chỉ di chuyển về phía trước và mỗi ký tự được xét tối đa một số lần hằng.
- Bộ nhớ: $\mathcal {O} (1)$ bộ nhớ phụ, không tính bộ nhớ lưu xâu đầu vào.
```cpp
#include <bits/stdc++.h>
using namespace std;

string S;

void solve(void)
{
    cin >> S;
    int N = S.length();
    S = ' ' + S;
    int j = 1;
    int ans = 0;
    for (int i = 1; i <= N; ++i)
    {
        while (j <= N && S[i] == S[j])
        {
            ++j;
        }
        ans = max(ans, j - i);
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