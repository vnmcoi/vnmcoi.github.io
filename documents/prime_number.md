
# Tuần 3: Số nguyên tố

## 1. Số nguyên tố

### 1.1. Định nghĩa và tính chất cơ bản

Trong toán học, số nguyên tố là một trong những khái niệm quan trọng nhất của số học.

Một số nguyên dương lớn hơn $1$ được gọi là **số nguyên tố** nếu nó chỉ có đúng hai ước số dương là $1$ và chính nó.

Ngược lại, những số nguyên dương lớn hơn $1$ nhưng có nhiều hơn hai ước số dương được gọi là **hợp số**.

Ví dụ, các số nguyên tố đầu tiên là:

$$
2, 3, 5, 7, 11, 13, 17, 19, \ldots
$$

Trong khi đó, các số $4, 6, 8, 9, 10, 12$ đều là hợp số.

Một số trường hợp đặc biệt cần lưu ý:

- Số $1$ không phải là số nguyên tố cũng không phải là hợp số.
- Số $0$ không phải là số nguyên tố.
- Số $2$ là số nguyên tố chẵn duy nhất. Mọi số nguyên tố khác đều là số lẻ.

**Tại sao số $1$ không phải là số nguyên tố?**

Theo định nghĩa, một số nguyên tố phải có đúng hai ước số dương phân biệt. Tuy nhiên, số $1$ chỉ có duy nhất một ước số dương là chính nó.

Vì vậy, $1$ không phải là số nguyên tố.

### 1.2. Phân tích thừa số nguyên tố

Một tính chất quan trọng của số nguyên tố là mọi số nguyên dương lớn hơn $1$ đều có thể được biểu diễn thành tích của các số nguyên tố.

Cách biểu diễn này được gọi là **phân tích thừa số nguyên tố**.

Ví dụ:

$$
24 = 2 \times 2 \times 2 \times 3
$$

Hay viết gọn:

$$
24 = 2^3 \times 3
$$

Tương tự:

$$
60 = 2^2 \times 3 \times 5
$$

Một kết quả quan trọng trong số học là **định lý cơ bản của số học**:

Mọi số nguyên dương lớn hơn $1$ đều có thể phân tích thành tích các số nguyên tố theo một cách duy nhất, nếu không xét thứ tự của các thừa số.

Chẳng hạn, dù chúng ta có thể viết:

$$
24 = 2 \times 2 \times 2 \times 3
$$

hoặc:

$$
24 = 3 \times 2 \times 2 \times 2
$$

thì bản chất các thừa số nguyên tố vẫn không thay đổi.

Tính chất này là cơ sở cho rất nhiều thuật toán trong số học, chẳng hạn như tìm ước số, tìm bội số chung nhỏ nhất và phân tích thừa số nguyên tố.

### 1.3. Ứng dụng trong bài toán đếm ước số

Từ việc phân tích thừa số nguyên tố, chúng ta có thể xây dựng một công thức tính nhanh số lượng ước số của một số nguyên dương.

Giả sử một số nguyên dương $N$ có dạng phân tích thừa số nguyên tố:

$$
N = p_1^{k_1} \times p_2^{k_2}
\times \cdots \times p_n^{k_n}
$$

Trong đó:

- $p_1,p_2,\ldots,p_n$ là các số nguyên tố phân biệt.
- $k_1,k_2,\ldots,k_n$ là số mũ tương ứng của từng thừa số nguyên tố.

Khi đó, số lượng ước số dương của $N$ được tính bằng:

$$
\boxed{
d(N)=(k_1+1)(k_2+1)\cdots(k_n+1)
}
$$

---

## 2. Kiểm tra số nguyên tố

Trong các bài toán lập trình, chúng ta thường gặp yêu cầu kiểm tra xem một số nguyên $x$ có phải là số nguyên tố hay không.

Ví dụ:

- Kiểm tra một số có phải là số nguyên tố.
- Đếm số lượng số nguyên tố trong một khoảng.
- Tìm số nguyên tố gần nhất với một số cho trước.
- Phân tích một số thành các thừa số nguyên tố.

Tùy thuộc vào giới hạn dữ liệu đầu vào và số lượng truy vấn, chúng ta có thể lựa chọn những thuật toán khác nhau.

### 2.1. Thuật toán kiểm tra cơ bản

Dựa vào định nghĩa số nguyên tố, một số nguyên tố chỉ có đúng hai ước số dương là $1$ và chính nó.

Vì vậy, một cách đơn giản để kiểm tra tính nguyên tố của $x$ là duyệt qua tất cả các số nguyên từ $1$ đến $x$, sau đó đếm số lượng ước số của nó.

Nếu số lượng ước số bằng $2$, ta kết luận $x$ là số nguyên tố.

Ngược lại, nếu số lượng ước số lớn hơn $2$, thì $x$ là hợp số.

**Mẫu tham khảo:**

```cpp
bool check(int x)
{
    int cnt = 0;

    for (int i = 1; i <= x; ++i)
    {
        if (x % i == 0)
        {
            ++cnt;
        }
    }

    return (x > 1 && cnt == 2);
}
```

Trong đoạn code trên:

- `x % i == 0` dùng để kiểm tra xem $i$ có phải là ước của $x$ hay không.
- `cnt` lưu số lượng ước số tìm được.
- Cuối cùng, chúng ta kiểm tra xem $x$ có lớn hơn $1$ và có đúng hai ước số hay không.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(x)$ vì chúng ta cần kiểm tra toàn bộ các số từ $1$ đến $x$.
- Bộ nhớ: $\mathcal{O}(1)$ vì chỉ sử dụng một số biến phụ.

Đây là thuật toán dễ hiểu và dễ cài đặt, tuy nhiên chưa thực sự hiệu quả khi $x$ có giá trị lớn.

### 2.2. Thuật toán cải tiến

Để cải thiện thuật toán trên, chúng ta cần quan sát một tính chất quan trọng của các ước số.

Giả sử một số nguyên dương $x$ là hợp số.

Khi đó, chắc chắn tồn tại hai số nguyên dương $a,b$ sao cho:

$$
a\times b=x
$$

Không mất tính tổng quát, chúng ta giả sử:

$$
a\leq b
$$

Khi đó:

$$
a^2\leq a\times b
$$

Mà:

$$
a\times b=x
$$

Nên:

$$
a^2\leq x
$$

Suy ra:

$$
\boxed{a\leq\sqrt{x}}
$$

Điều này cho chúng ta một nhận xét rất quan trọng:

**Nếu $x$ là hợp số thì chắc chắn tồn tại ít nhất một ước số dương khác $1$ không vượt quá $\sqrt{x}$.**

Nói cách khác, nếu không tìm thấy ước số nào của $x$ trong khoảng:

$$
[2;\sqrt{x}]
$$

thì $x$ chắc chắn là số nguyên tố, với điều kiện $x>1$.

Vì vậy, thay vì duyệt toàn bộ khoảng $[1;x]$, chúng ta chỉ cần kiểm tra từ $2$ đến $\sqrt{x}$.

**Mẫu tham khảo:**

```cpp
bool check(int x)
{
    if (x <= 1)
    {
        return false;
    }

    for (int i = 2; 1LL * i * i <= x; ++i)
    {
        if (x % i == 0)
        {
            return false;
        }
    }

    return true;
}
```

**Lưu ý:**

Trong điều kiện vòng lặp, chúng ta sử dụng:

```cpp
1LL * i * i <= x
```

Thay vì:

```cpp
i * i <= x
```

Nguyên nhân là khi `i` có giá trị lớn, phép nhân `i * i` có thể vượt quá giới hạn của kiểu dữ liệu `int`, dẫn đến tràn số.

Sử dụng `1LL` giúp phép nhân được thực hiện với kiểu `long long`.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(\sqrt{x})$ vì chúng ta chỉ cần kiểm tra các số từ $2$ đến $\sqrt{x}$.
- Bộ nhớ: $\mathcal{O}(1)$.

Đây là thuật toán kiểm tra số nguyên tố cơ bản mà chúng ta thường sử dụng trong lập trình thi đấu.

### 2.3. Tối ưu bằng cách nhảy nguyên tố

Chúng ta có thể tiếp tục cải thiện thuật toán kiểm tra số nguyên tố bằng cách quan sát hai số nguyên tố đầu tiên là $2$ và $3$.

Nếu một số nguyên $x$ lớn hơn $3$ là số nguyên tố thì chắc chắn:

$$
x\bmod2\neq0
$$

và:

$$
x\bmod3\neq0
$$

Điều này có nghĩa là chúng ta có thể loại bỏ tất cả các số chia hết cho $2$ hoặc $3$ mà không cần kiểm tra chúng trong vòng lặp.

Để hiểu rõ hơn, chúng ta xét các số nguyên liên tiếp dưới dạng:

$$
6k,\ 6k+1,\ 6k+2,\ 6k+3,\ 6k+4,\ 6k+5
$$

Trong đó:

- $6k$ chia hết cho $2$ và $3$.
- $6k+2$ chia hết cho $2$.
- $6k+3$ chia hết cho $3$.
- $6k+4$ chia hết cho $2$.

Như vậy, những trường hợp còn lại là:

$$
6k+1\quad\text{và}\quad6k+5
$$

Hay có thể viết:

$$
\boxed{6k\pm1}
$$

Từ đó, chúng ta nhận thấy mọi số nguyên tố lớn hơn $3$ đều có dạng $6k+1$ hoặc $6k+5$.

**Lưu ý:** Đây chỉ là điều kiện cần, không phải điều kiện đủ để một số là số nguyên tố.

Ví dụ:

$$
25=6\times4+1
$$

Nhưng $25$ không phải là số nguyên tố vì:

$$
25=5\times5
$$

Vì vậy, dù đã loại bỏ được các bội số của $2$ và $3$, chúng ta vẫn phải tiếp tục kiểm tra những ước số còn lại.

**Mẫu tham khảo:**

```cpp
bool check(long long x)
{
    if (x == 2 || x == 3)
    {
        return true;
    }

    if (x <= 1 || x % 2 == 0 || x % 3 == 0)
    {
        return false;
    }

    for (long long i = 5; i * i <= x; i += 6)
    {
        if (x % i == 0 || x % (i + 2) == 0)
        {
            return false;
        }
    }

    return true;
}
```

**Giải thích vòng lặp:**

Chúng ta bắt đầu từ $5$, sau đó mỗi lần tăng $6$ đơn vị.

Với mỗi giá trị $i$, chúng ta kiểm tra hai số:

$$
i\quad\text{và}\quad i+2
$$

Các số được kiểm tra lần lượt là:

$$
5,7,11,13,17,19,23,25,\ldots
$$

Đây chính là những số có dạng $6k-1$ hoặc $6k+1$.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(\sqrt{x})$.
- Bộ nhớ: $\mathcal{O}(1)$.

Mặc dù số lượng lần kiểm tra giảm đáng kể so với thuật toán trước, độ phức tạp tiệm cận vẫn là $\mathcal{O}(\sqrt{x})$.

Nói cách khác, đây là một cách tối ưu hằng số thời gian chứ không làm thay đổi bậc độ phức tạp.

Thực tế, chúng ta có thể tiếp tục xây dựng những điều kiện để loại bỏ thêm nhiều ứng viên, nhưng điều đó thường khiến code phức tạp hơn mà không đem lại lợi ích đáng kể đối với bài toán kiểm tra cơ bản.

### 2.4. Thuật toán kiểm tra nguyên tố xác suất

Đối với những số nguyên có giá trị rất lớn, việc kiểm tra từng ước số đến $\sqrt{x}$ có thể không còn đáp ứng được giới hạn thời gian.

Trong trường hợp này, chúng ta có thể sử dụng những thuật toán kiểm tra nguyên tố có tính xác suất hoặc dựa trên các phép kiểm tra nhân chứng.

Một thuật toán tiêu biểu là Miller–Rabin.

Khác với những phương pháp trước, Miller–Rabin không kiểm tra trực tiếp toàn bộ các ước số của một số. Thay vào đó, thuật toán sử dụng các tính chất toán học liên quan đến đồng dư modulo để xác định một số có khả năng là hợp số hay không.

Một số kết quả của thuật toán:

- Nếu thuật toán kết luận một số là hợp số, kết luận đó là chính xác.
- Nếu thuật toán kết luận một số có khả năng là nguyên tố, vẫn tồn tại xác suất sai tùy thuộc vào số lần kiểm tra và cách lựa chọn cơ sở kiểm tra.

Trong lập trình thi đấu, có những cách lựa chọn cơ sở kiểm tra giúp Miller–Rabin hoạt động tất định trên toàn bộ miền số nguyên 64-bit.

Vì đây là một nội dung nâng cao và không thường xuyên cần thiết trong các bài toán cơ bản, các bạn có thể tham khảo thêm bài viết của VNOI:

https://wiki.vnoi.info/algo/algebra/primality_check.md

### 2.5. Sàng Eratosthenes

Trong những phần trước, chúng ta đã biết cách kiểm tra tính nguyên tố của một số nguyên bằng thuật toán có độ phức tạp $\mathcal{O}(\sqrt{x})$.

Tuy nhiên, hãy xét một bài toán khác:

**Yêu cầu:** Kiểm tra tính nguyên tố của tất cả các số nguyên trong khoảng $[1;N]$.

Chúng ta hoàn toàn có thể sử dụng thuật toán kiểm tra nguyên tố vừa học để kiểm tra từng số.

Tuy nhiên, nếu thực hiện độc lập cho tất cả các số, tổng thời gian có thể lên đến:

$$
\mathcal{O}(N\sqrt{N})
$$

Đây là một cách làm chưa hiệu quả nếu $N$ đủ lớn.

Để giải quyết vấn đề này, chúng ta sử dụng một thuật toán có tên là **sàng Eratosthenes**.

**Tư tưởng:**

Thay vì kiểm tra từng số xem nó có phải là số nguyên tố hay không, chúng ta sẽ loại bỏ trực tiếp những số chắc chắn là hợp số.

Một nhận xét đơn giản là:

Nếu $p$ là số nguyên tố thì mọi bội số của $p$ lớn hơn $p$ đều là hợp số.

Ví dụ, với $p=2$, những bội số lớn hơn $2$ là:

$$
4,6,8,10,12,\ldots
$$

Tất cả đều là hợp số.

Tương tự, với $p=3$, những bội số lớn hơn $3$ là:

$$
6,9,12,15,18,\ldots
$$

Chúng ta có thể loại bỏ những số này khỏi danh sách các ứng viên.

Quá trình thực hiện như sau:

1. Ban đầu, giả sử tất cả các số từ $2$ đến $N$ đều là số nguyên tố.
2. Bắt đầu từ số nguyên tố nhỏ nhất là $2$, đánh dấu tất cả bội số lớn hơn $2$ của nó là hợp số.
3. Tìm số tiếp theo chưa bị đánh dấu. Số đó chính là một số nguyên tố.
4. Tiếp tục đánh dấu tất cả bội số lớn hơn của số nguyên tố vừa tìm được.
5. Lặp lại quá trình cho đến khi hoàn thành.

Sau khi kết thúc, những số chưa bị đánh dấu chính là các số nguyên tố.


**Mẫu tham khảo:**

```cpp
const int mxN = 1000005;

bool prime[mxN];

void eratosthenes(int N)
{
    memset(prime, true, sizeof(prime));

    prime[0] = prime[1] = false;

    for (int i = 2; 1LL * i * i <= N; ++i)
    {
        if (prime[i])
        {
            for (int j = i * i; j <= N; j += i)
            {
                prime[j] = false;
            }
        }
    }
}
```

Trong đoạn code trên:

- `prime[i] == true` có nghĩa là chúng ta đang xem $i$ là số nguyên tố.
- `prime[i] == false` có nghĩa là $i$ đã được xác định là hợp số hoặc không phải số nguyên tố.
- `prime[0]` và `prime[1]` được gán `false` vì $0$ và $1$ không phải số nguyên tố.
- Vòng lặp ngoài tìm các số nguyên tố chưa bị đánh dấu.
- Vòng lặp trong đánh dấu tất cả bội số của số nguyên tố đó.

Sau khi thuật toán kết thúc, chúng ta có thể kiểm tra một số $x$ có phải là số nguyên tố hay không bằng cách:

```cpp
if (prime[x])
{
    // x là số nguyên tố
}
```

**Tại sao vòng lặp ngoài chỉ cần chạy đến $\sqrt{N}$?**

Từ tính chất đã học ở phần kiểm tra số nguyên tố, nếu một số là hợp số thì nó luôn có ít nhất một ước số không vượt quá căn bậc hai của nó.

Vì vậy, khi đã xử lý tất cả các số nguyên tố không vượt quá $\sqrt{N}$, mọi hợp số trong khoảng $[1;N]$ đều đã được đánh dấu.

Do đó, chúng ta không cần tiếp tục vòng lặp ngoài đến $N$.

**Độ phức tạp**

- Thời gian: $\mathcal{O}(N\log\log N)$.
- Bộ nhớ: $\mathcal{O}(N)$.

Trong đó, $N$ là giới hạn trên của khoảng cần sàng.

Để hiểu thêm về độ phức tạp, chúng ta có thể xét số lần đánh dấu của từng số nguyên tố $p$.

Số lượng bội số cần đánh dấu của $p$ xấp xỉ:

$$
\frac{N}{p}
$$

Vì vậy, tổng số thao tác đánh dấu có liên quan đến biểu thức:

$$
N\left(
\frac12+\frac13+\frac15+\frac17+\cdots
\right)
$$

Trong đó các mẫu số là những số nguyên tố.

Một kết quả trong lý thuyết số cho biết tổng nghịch đảo của các số nguyên tố không vượt quá $N$ có bậc tăng trưởng $\mathcal{O}(\log\log N)$.

Do đó, độ phức tạp thời gian của sàng Eratosthenes là:

$$
\boxed{\mathcal{O}(N\log\log N)}
$$

Đây là một thuật toán rất hiệu quả khi chúng ta cần tìm toàn bộ số nguyên tố trong một khoảng có giới hạn trên không quá lớn.

### 2.6. Một số lưu ý khi sử dụng sàng Eratosthenes

Mặc dù sàng Eratosthenes có độ phức tạp tốt, chúng ta vẫn cần chú ý đến giới hạn bộ nhớ.

Với mảng:

```cpp
bool prime[mxN];
```

chúng ta cần cấp phát đủ bộ nhớ để lưu trữ tất cả các số từ $0$ đến $N$.

Nếu $N$ quá lớn, việc lưu toàn bộ mảng có thể không còn khả thi.

Ngoài ra, nếu chỉ cần kiểm tra một số lượng nhỏ các số, sử dụng sàng có thể không hiệu quả bằng thuật toán kiểm tra nguyên tố $\mathcal{O}(\sqrt{x})$.

Vì vậy, cần lựa chọn thuật toán dựa trên yêu cầu cụ thể của bài toán.

---

## 3. Bài tập tự làm

Các bài tập dưới đây được sắp xếp theo mức độ tăng dần. Mục tiêu không chỉ là tìm được kết quả đúng mà còn phải hiểu được bản chất toán học và lý do các thuật toán hoạt động.

Đối với những bài yêu cầu chứng minh, hãy trình bày đầy đủ lập luận thay vì chỉ ghi lại công thức đã học.

### Bài 1. Công thức đếm số lượng ước số

Cho một số nguyên dương $N$ có dạng phân tích thừa số nguyên tố:

$$
N=p_1^{k_1}\times p_2^{k_2}
\times\cdots\times p_n^{k_n}
$$

Chứng minh rằng số lượng ước số dương của $N$ được tính bằng:

$$
\boxed{
d(N)=(k_1+1)(k_2+1)\cdots(k_n+1)
}
$$

Yêu cầu:

1. Giải thích dạng tổng quát của một ước số của $N$.
2. Xác định số cách lựa chọn số mũ của từng thừa số nguyên tố.
3. Sử dụng quy tắc nhân để suy ra công thức.

### Bài 2. Tính chất ước số

Cho hai số nguyên dương $a,b$ thỏa mãn:

$$
a\times b=N
$$

Chứng minh rằng nếu $a>\sqrt{N}$ thì:

$$
b<\sqrt{N}
$$

Từ đó giải thích tại sao khi kiểm tra số nguyên tố, chúng ta chỉ cần duyệt đến $\sqrt{N}$.

### Bài 3. Tính chất của dạng $6k\pm1$

Chứng minh rằng mọi số nguyên tố lớn hơn $3$ đều có dạng:

$$
6k+1\quad\text{hoặc}\quad6k-1
$$

Trong đó $k$ là một số nguyên dương.

Sau đó, hãy giải thích tại sao điều kiện này không đủ để kết luận một số là số nguyên tố.

Cho ví dụ minh họa.

### Bài 4. Phân tích độ phức tạp

Xét biểu thức:

$$
N+\frac{N}{2}+\frac{N}{3}
+\cdots+\frac{N}{N}
$$

Chứng minh rằng:

$$
\sum_{i=1}^{N}\frac{N}{i}
=\mathcal{O}(N\log N)
$$

Gợi ý: Có thể sử dụng tính chất của tổng điều hòa và so sánh với tích phân.

### Bài 5. Sàng Eratosthenes

Xét thuật toán sàng Eratosthenes.

Hãy giải thích tại sao vòng lặp đánh dấu bội số của $i$ lại bắt đầu từ:

$$
j=i\times i
$$

thay vì:

$$
j=i\times2
$$

Yêu cầu đưa ra một ví dụ cụ thể để minh họa những số đã được đánh dấu trước đó.

### Bài 6. Tối ưu thuật toán

Hãy xây dựng một chương trình C++ thực hiện những yêu cầu sau:

Cho hai số nguyên $L,R$.

1. Đếm số lượng số nguyên tố trong đoạn $[L,R]$.
2. In ra tất cả các số nguyên tố trong đoạn đó.
3. Tìm số nguyên tố nhỏ nhất và lớn nhất trong đoạn.

Hãy lựa chọn thuật toán phù hợp và phân tích độ phức tạp của chương trình.

### Bài 7. Nâng cao: Định lý nhỏ Fermat

Trong tuần trước, chúng ta đã tìm hiểu về đồng dư modulo và nghịch đảo modulo.

Một tính chất quan trọng liên quan đến số nguyên tố là định lý nhỏ Fermat:

Nếu $p$ là số nguyên tố và $a$ là số nguyên không chia hết cho $p$, thì:

$$
\boxed{a^{p-1}\equiv1\pmod p}
$$

Hãy tìm hiểu và chứng minh định lý trên.

Sau đó, giải thích tại sao tính chất này có thể được sử dụng để tìm nghịch đảo modulo:

$$
\boxed{a^{-1}\equiv a^{p-2}\pmod p}
$$

Trong đó $p$ là số nguyên tố và $p\nmid a$.

Đây là một kiến thức quan trọng trong lập trình thi đấu, đặc biệt khi làm việc với các phép toán modulo và lũy thừa có số mũ lớn.
