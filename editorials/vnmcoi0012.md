Bài toán Tháp Hà Nội có thể giải bằng đệ quy, dựa trên việc chia bài toán di chuyển $n$ đĩa thành các bài toán nhỏ hơn.

Gọi $f_{n}$ là số bước di chuyển tối thiểu cần thiết để chuyển $n$ đĩa từ cột bắt đầu $a$ sang cột kết thúc $b$, sử dụng cột trung gian $c$.

## Trường hợp cơ sở

Với $n=1$, chỉ có một đĩa cần di chuyển. Ta di chuyển trực tiếp đĩa đó từ cột $a$ sang cột $b$.

Do đó:

$$ f(1)=1 $$

## Hệ thức đệ quy

Với $n>1$, để di chuyển $n$ đĩa từ cột $a$ sang cột $b$, ta thực hiện ba bước:

1. Di chuyển $n-1$ đĩa trên cùng từ cột $a$ sang cột trung gian $c$, sử dụng cột $b$ làm cột phụ.
2. Di chuyển đĩa lớn nhất từ cột $a$ sang cột $b$.
3. Di chuyển $n-1$ đĩa từ cột trung gian $c$ sang cột đích $b$, sử dụng cột $a$ làm cột phụ.

Như vậy, số bước di chuyển được xác định bởi:

$$ f_{n}=2 \times f_{n-1}+1 $$

Giải hệ thức đệ quy này, ta thu được:

$$ f_{n}=2^n-1 $$

Vì vậy, số bước di chuyển tối thiểu cần thực hiện là $2^n-1$.

## Cách xác định cột trung gian

Ba cột được đánh số $1,2,3$. Khi biết cột bắt đầu $a$ và cột kết thúc $b$, cột trung gian $c$ được xác định bởi:

$$ c=6-a-b $$

Do tổng của ba số $1+2+3=6$, công thức trên cho ta cột còn lại.

Hàm đệ quy sẽ thực hiện lần lượt ba bước đã nêu, đồng thời in ra từng thao tác di chuyển đĩa. Khi $n=1$, hàm in thao tác di chuyển trực tiếp từ cột bắt đầu sang cột kết thúc.

Độ phức tạp:

- Thời gian: $\mathcal{O} (2^n)$, do số thao tác di chuyển tối thiểu là $2^n-1$.
- Bộ nhớ: $\mathcal{O} (n)$, do độ sâu tối đa của ngăn xếp đệ quy là $n$.

```cpp
#include <bits/stdc++.h>
using namespace std;

int N;

void dewuy(int n, int a, int b)
{
    if (n == 1)
    {
        cout << a << ' ' << b << '\n';
        return;
    }
    int c = 6 - (a + b);
    dewuy(n - 1, a, c);
    cout << a << ' ' << b << '\n';
    dewuy(n - 1, c, b);
}

void solve(void)
{
    cin >> N;
    cout << pow(2, N) - 1 << '\n';
    dewuy(N, 1, 3);
}

int main(void)
{
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    solve();
    return 0;
}
```