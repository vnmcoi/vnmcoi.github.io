## 1. Bài toán đếm

Bài toán yêu cầu đếm số cách đặt hai quân mã trên bàn cờ $k \times k$ sao cho chúng không ăn nhau. Hai quân mã được xem là không phân biệt, vì vậy ta không đếm các hoán vị của cùng một cách đặt.

Thay vì đếm trực tiếp số cách đặt hai quân mã không ăn nhau, ta sử dụng quy tắc bù: lấy tổng số cách đặt hai quân mã bất kỳ rồi trừ đi số cách đặt khiến chúng ăn nhau.

Một quân mã có thể ăn quân còn lại nếu hai quân nằm tại hai ô có độ lệch tọa độ là $(1,2)$ hoặc $(2,1)$. Các cặp ô như vậy có thể được biểu diễn bằng những hình chữ nhật kích thước $2 \times 3$ hoặc $3 \times 2$.

Trong mỗi hình chữ nhật $2 \times 3$ hoặc $3 \times 2$, có đúng hai cách đặt hai quân mã để chúng ăn nhau. Vì vậy, ta có thể đếm số cặp ô mà hai quân mã có thể ăn nhau thông qua số hình chữ nhật thuộc hai kích thước này.

## 2. Công thức đếm

Trên bàn cờ $k \times k$, có tổng cộng $k^2$ ô. Ta chọn hai ô khác nhau để đặt hai quân mã, nên tổng số cách đặt là:

$$ \frac{k^2(k^2-1)}{2} $$

Tiếp theo, ta đếm số cách đặt khiến hai quân mã ăn nhau.

- Số hình chữ nhật kích thước $2 \times 3$ là $(k-1)(k-2)$.
- Số hình chữ nhật kích thước $3 \times 2$ cũng là $(k-2)(k-1)$.

Mỗi hình chữ nhật có hai cách đặt hai quân mã ăn nhau. Do đó, tổng số cách đặt khiến hai quân mã ăn nhau là:

$$ 2\big((k-1)(k-2)+(k-2)(k-1)\big) $$

Khi $k < 3$, không tồn tại hình chữ nhật $2 \times 3$ hoặc $3 \times 2$, nên số cách đặt khiến hai quân mã ăn nhau bằng $0$.

Vậy số cách đặt hai quân mã không ăn nhau trên bàn cờ $k \times k$ là:

$$ \boxed{ \frac{k^2(k^2-1)}{2} -4(k-1)(k-2) } $$

Với $k=1,2$, ta xem số cách đặt khiến hai quân mã ăn nhau bằng $0$. Áp dụng công thức cho từng giá trị $k=1,2,\ldots,n$, ta thu được kết quả cần in ra.

```cpp
#include <bits/stdc++.h>
using namespace std;

int n;

void solve(void)
{
    cin >> n;
    for (int k = 1; k <= n; ++k)
    {
        long long sum = 1LL * k * k * ((1LL * k * k) - 1) / 2;
        long long vertical = 1LL * max(0, k - 2) * max(0, k - 1);
        long long horizontal = 1LL * max(0, k - 1) * max(0, k - 2);
        cout << sum - 2 * (vertical + horizontal) << '\n';
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