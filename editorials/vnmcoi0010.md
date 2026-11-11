Vì $k \le 10^{18}$, chúng ta không thể tạo toàn bộ chuỗi rồi truy vấn trực tiếp. Thay vào đó, ta cần xác định chữ số cần tìm bằng cách tính toán.

Nhận xét rằng các số nguyên dương có thể được chia thành từng nhóm dựa trên số lượng chữ số:

- Nhóm số có $1$ chữ số: từ $1$ đến $9$, chứa $9$ chữ số.
- Nhóm số có $2$ chữ số: từ $10$ đến $99$, chứa $90 \cdot 2 = 180$ chữ số.
- Nhóm số có $3$ chữ số: từ $100$ đến $999$, chứa $900 \cdot 3 = 2700$ chữ số.
- Tổng quát, nhóm các số có $c$ chữ số chứa $9 \cdot 10^{c-1} \cdot c$ chữ số.

Đầu tiên, chuyển vị trí $k$ từ chỉ số bắt đầu bằng $1$ sang chỉ số bắt đầu bằng $0$ bằng cách giảm $k$ đi $1$.

Gọi:

- $a$ là số đầu tiên trong nhóm đang xét.
- $b$ là số cuối cùng trong nhóm đang xét.
- $c$ là số chữ số của mỗi số thuộc nhóm đó.

Số chữ số của nhóm hiện tại là:

$$ c \cdot (b-a+1) $$

Nếu $k$ lớn hơn hoặc bằng số chữ số của nhóm này, ta trừ số chữ số đó khỏi $k$ và chuyển sang nhóm tiếp theo. Quá trình dừng lại khi $k$ nằm trong nhóm hiện tại.

Sau đó, ta xác định số chứa chữ số cần tìm:

$$ q = \left\lfloor \frac{k}{c} \right\rfloor $$

Và vị trí của chữ số bên trong số đó:

$$ r = k \bmod c $$

Số cần xét là $a+q$. Chuyển số này thành chuỗi, chữ số tại chỉ số $r$ chính là kết quả của truy vấn.

Độ phức tạp: Với mỗi truy vấn, ta duyệt qua các nhóm chữ số. Do số chữ số của $k$ không vượt quá $19$, mỗi truy vấn chỉ cần $\mathcal {O} (\log k)$ thời gian.

```cpp
#include <bits/stdc++.h>
using namespace std;

void solve(void)
{
    long long k;
    cin >> k;
    --k;
    long long a = 1;
    long long b = 9;
    long long c = 1;
    while (k - c * (b - a + 1) >= 0)
    {
        k -= c * (b - a + 1);
        a = a * 10;
        b = b * 10 + 9;
        ++c;
    }
    long long q = k / c;
    long long r = k % c;
    string s = to_string(a + q);
    cout << s[r] << '\n';
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int Q;
    cin >> Q;
    while (Q--)
    {
        solve();
    }
    return 0;
}
```