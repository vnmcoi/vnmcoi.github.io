# Tuần 2 — Mở rộng: Đồng dư và nghịch đảo modulo

## 1. Ôn tập: Đồng dư modulo

### 1.1. Phép modulo là gì?

Trong tuần 1, chúng ta đã học rằng khi chia một số nguyên $a$ cho một số nguyên dương $m$, luôn tồn tại duy nhất hai số nguyên $q,r$ sao cho:

$$
a=mq+r
$$

với điều kiện:

$$
0\le r<m.
$$

Trong đó:

- $a$ là số bị chia.
- $m$ là số chia.
- $q$ là thương nguyên.
- $r$ là số dư.

Phép toán modulo trả về số dư $r$.

Ví dụ:

$$
17=3\times5+2.
$$

Do đó:

$$
17\bmod3=2.
$$

Tương tự:

$$
8\bmod3=2.
$$

Như vậy, hai số $17$ và $8$ có cùng số dư khi chia cho $3$.

### 1.2. Đồng dư modulo là gì?

Trong toán học, chúng ta thường cần diễn đạt mối quan hệ giữa hai số có cùng số dư.

Thay vì phải viết hai phép chia riêng biệt, chúng ta sử dụng một ký hiệu toán học gọi là **đồng dư modulo**.

Cho hai số nguyên $a,b$ và một số nguyên dương $m$.

Nếu $a$ và $b$ có cùng số dư khi chia cho $m$, chúng ta viết:

$$
\boxed{a\equiv b\pmod m}
$$

Biểu thức này được đọc là:

$a$ đồng dư với $b$ theo modulo $m$.

Ví dụ:

$$
17\bmod3=2
$$

và:

$$
8\bmod3=2.
$$

Vì hai số có cùng số dư nên:

$$
\boxed{17\equiv8\pmod3}
$$

Một cách diễn đạt tương đương của định nghĩa đồng dư là:

Hai số nguyên $a,b$ đồng dư theo modulo $m$ nếu hiệu của chúng có thể viết dưới dạng một bội nguyên của $m$.

Tức là tồn tại một số nguyên $k$ sao cho:

$$
a-b=km.
$$

Ví dụ:

$$
17-8=9=3\times3.
$$

Do đó:

$$
17\equiv8\pmod3.
$$

Tương tự:

$$
-1-2=-3=3\times(-1).
$$

Vì vậy:

$$
-1\equiv2\pmod3.
$$

**Lưu ý:** Đồng dư không đồng nghĩa với bằng nhau.

Chẳng hạn:

$$
17\equiv8\pmod3
$$

là đúng, nhưng:

$$
17\ne8.
$$

Hai số đồng dư có thể có giá trị rất khác nhau. Điều quan trọng là chúng có cùng số dư khi chia cho modulo đang xét.

### 1.3. Các phép biến đổi đồng dư cơ bản

Giả sử:

$$
a\equiv b\pmod m.
$$

Điều này có nghĩa là hai số $a,b$ có cùng số dư khi chia cho $m$.

Từ đó, chúng ta có thể thực hiện những phép biến đổi sau.

**Phép cộng**

Cộng cùng một số nguyên $c$ vào cả hai vế:

$$
\boxed{a+c\equiv b+c\pmod m}
$$

**Phép trừ**

Trừ cùng một số nguyên $c$ ở cả hai vế:

$$
\boxed{a-c\equiv b-c\pmod m}
$$

**Phép nhân**

Nhân cả hai vế với cùng một số nguyên $c$:

$$
\boxed{ac\equiv bc\pmod m}
$$

Các tính chất này có thể được giải thích trực tiếp từ định nghĩa đồng dư.

Ví dụ, giả sử:

$$
a-b=km.
$$

Khi cộng $c$ vào cả hai vế, hiệu của chúng vẫn là:

$$
(a+c)-(b+c)=a-b=km.
$$

Do đó, tính đồng dư vẫn được bảo toàn.

Tương tự, khi nhân cả hai vế với $c$:

$$
ac-bc=c(a-b)=ckm.
$$

Vì $ck$ vẫn là số nguyên, hai số mới vẫn đồng dư theo modulo $m$.

### 1.4. Phép nhân hai đồng dư

Một tính chất quan trọng khác là:

Nếu:

$$
a\equiv b\pmod m
$$

và:

$$
c\equiv d\pmod m,
$$

thì:

$$
\boxed{ac\equiv bd\pmod m}
$$

Điều này cho phép chúng ta rút gọn các thừa số trong một biểu thức trước khi thực hiện phép nhân.

Ví dụ:

$$
17\times23\pmod5.
$$

Vì:

$$
17\equiv2\pmod5
$$

và:

$$
23\equiv3\pmod5,
$$

nên:

$$
17\times23\equiv2\times3\pmod5.
$$

Do đó:

$$
17\times23\equiv1\pmod5.
$$

Thay vì thực hiện phép nhân hai số lớn, chúng ta chỉ cần nhân hai số dư tương ứng.

### 1.5. Có thể chia hai vế của một đồng dư không?

Đây là một điểm rất dễ gây nhầm lẫn.

Trong đại số thông thường, nếu:

$$
ac=bc,
$$

thì khi $c\ne0$, chúng ta có thể chia cả hai vế cho $c$.

Tuy nhiên, đối với đồng dư modulo, phép chia không phải lúc nào cũng được phép thực hiện.

Ví dụ:

$$
2\times3\equiv2\times0\pmod6.
$$

Vế trái bằng $6$, còn vế phải bằng $0$. Hai số này đồng dư modulo $6$.

Nhưng nếu chia cả hai vế cho $2$, chúng ta nhận được:

$$
3\equiv0\pmod6.
$$

Điều này không đúng vì $3$ và $0$ không có cùng số dư khi chia cho $6$.

Vậy tại sao phép chia lại gặp vấn đề?

Nguyên nhân là trong modulo, một số không phải lúc nào cũng có phép chia ngược tương ứng. Để chia cho một số, chúng ta cần một khái niệm gọi là nghịch đảo modulo.

Nội dung này sẽ được tìm hiểu ở phần sau.

---

## 2. Giải phương trình modulo

### 2.1. Phương trình modulo là gì?

Một phương trình modulo là phương trình có chứa quan hệ đồng dư.

Ví dụ:

$$
5+x\equiv1\pmod3.
$$

Trong đó:

- $x$ là biến cần tìm.
- $5$ và $1$ là các số nguyên đã biết.
- $3$ là modulo.

Mục tiêu là tìm những số nguyên $x$ thỏa mãn phương trình.

Khác với phương trình đại số thông thường, một phương trình modulo có thể có nhiều nghiệm nguyên khác nhau.

Ví dụ:

$$
x\equiv2\pmod3.
$$

Khi đó, tất cả các số nguyên có dạng:

$$
x=3k+2,\qquad k\in\mathbb Z
$$

đều là nghiệm.

Một số nghiệm cụ thể là:

$$
-4,-1,2,5,8,11,\ldots
$$

Những số này khác nhau nhưng đều thuộc cùng một lớp đồng dư modulo $3$.

### 2.2. Phương trình dạng tổng

Xét phương trình:

$$
a+x\equiv b\pmod m.
$$

Chúng ta trừ $a$ ở cả hai vế:

$$
a+x-a\equiv b-a\pmod m.
$$

Vì:

$$
a-a=0,
$$

nên:

$$
\boxed{x\equiv b-a\pmod m}
$$

Ví dụ, giải phương trình:

$$
5+x\equiv1\pmod3.
$$

Ta có:

$$
x\equiv1-5\pmod3.
$$

Suy ra:

$$
x\equiv-4\pmod3.
$$

Vì:

$$
-4\equiv2\pmod3,
$$

nên:

$$
\boxed{x\equiv2\pmod3}
$$

### 2.3. Phương trình dạng hiệu thứ nhất

Xét phương trình:

$$
a-x\equiv b\pmod m.
$$

Chúng ta có thể biến đổi:

$$
-x\equiv b-a\pmod m.
$$

Nhân cả hai vế với $-1$:

$$
\boxed{x\equiv a-b\pmod m}
$$

Ví dụ:

$$
8-x\equiv3\pmod5.
$$

Ta có:

$$
x\equiv8-3\pmod5.
$$

Suy ra:

$$
x\equiv5\equiv0\pmod5.
$$

Do đó:

$$
\boxed{x\equiv0\pmod5}
$$

### 2.4. Phương trình dạng hiệu thứ hai

Xét phương trình:

$$
x-a\equiv b\pmod m.
$$

Cộng $a$ vào cả hai vế:

$$
\boxed{x\equiv a+b\pmod m}
$$

Ví dụ:

$$
x-7\equiv2\pmod4.
$$

Ta có:

$$
x\equiv7+2\pmod4.
$$

Vậy:

$$
x\equiv9\equiv1\pmod4.
$$

### 2.5. Phương trình có phép nhân

Ngoài những dạng trên, chúng ta còn gặp phương trình:

$$
\boxed{ax\equiv b\pmod m}
$$

Đây là dạng tổng quát hơn vì hệ số của biến $x$ không nhất thiết bằng $1$ hoặc $-1$.

Chẳng hạn:

$$
3x\equiv2\pmod7.
$$

Để giải phương trình này, chúng ta cần tìm một số có thể nhân với $3$ để đưa hệ số của $x$ về $1$ theo modulo $7$.

Nói cách khác, chúng ta cần tìm nghịch đảo modulo của $3$.

Tuy nhiên, trước khi nghiên cứu nghịch đảo modulo một cách đầy đủ, chúng ta cần hiểu ước chung lớn nhất và cách tìm nó.

---

## 3. Ước chung lớn nhất và bội chung nhỏ nhất

### 3.1. Một số khái niệm cần thiết

Trong phần này, chúng ta cần sử dụng khái niệm ước số.

Cho hai số nguyên $a,b$, với $b\ne0$.

Ta nói $b$ là ước của $a$ nếu tồn tại một số nguyên $k$ sao cho:

$$
a=bk.
$$

Khi đó, chúng ta ký hiệu:

$$
b\mid a.
$$

Ví dụ:

$$
3\mid12
$$

vì:

$$
12=3\times4.
$$

Ngược lại:

$$
5\nmid12
$$

vì không tồn tại số nguyên $k$ sao cho $12=5k$.

Những khái niệm về ước số, bội số và các tính chất chia hết sẽ được nghiên cứu có hệ thống hơn trong tuần 3. Ở đây, chúng ta chỉ sử dụng những kiến thức cần thiết để xây dựng thuật toán tìm ước chung lớn nhất.

### 3.2. Ước chung lớn nhất là gì?

Ước chung của hai số nguyên là một số có thể chia hết cả hai số đó.

Ước chung lớn nhất là ước chung dương lớn nhất của hai số nguyên.

Ký hiệu:

$$
\gcd(a,b).
$$

Trong đó, $\gcd$ là viết tắt của cụm từ *greatest common divisor*.

Ví dụ, các ước dương của $12$ là:

$$
1,2,3,4,6,12.
$$

Các ước dương của $18$ là:

$$
1,2,3,6,9,18.
$$

Những ước chung dương của $12$ và $18$ là:

$$
1,2,3,6.
$$

Số lớn nhất trong các ước chung đó là $6$.

Do đó:

$$
\boxed{\gcd(12,18)=6}
$$

Đối với số nguyên âm, dấu của số không làm thay đổi các ước của nó.

Vì vậy, chúng ta quy ước:

$$
\boxed{\gcd(a,b)=\gcd(|a|,|b|)}
$$

Ví dụ:

$$
\gcd(-12,18)=6.
$$

Ước chung lớn nhất luôn được lấy là số không âm.

### 3.3. Bội chung nhỏ nhất là gì?

Một số nguyên được gọi là bội của số nguyên $a\ne0$ nếu nó có thể biểu diễn dưới dạng:

$$
ak,\qquad k\in\mathbb Z.
$$

Bội chung của hai số nguyên là số có thể biểu diễn dưới dạng bội của cả hai số đó.

Bội chung nhỏ nhất là bội chung dương nhỏ nhất của hai số nguyên khác $0$.

Ký hiệu:

$$
\operatorname{lcm}(a,b).
$$

Trong đó, $\operatorname{lcm}$ là viết tắt của cụm từ *least common multiple*.

Ví dụ, các bội dương của $4$ là:

$$
4,8,12,16,20,24,\ldots
$$

Các bội dương của $6$ là:

$$
6,12,18,24,30,\ldots
$$

Những bội chung dương của $4$ và $6$ là:

$$
12,24,36,\ldots
$$

Bội chung dương nhỏ nhất là $12$.

Vậy:

$$
\boxed{\operatorname{lcm}(4,6)=12}
$$

Tương tự như UCLN:

$$
\operatorname{lcm}(a,b)
=
\operatorname{lcm}(|a|,|b|).
$$

### 3.4. Mối liên hệ giữa UCLN và BCNN

Với hai số nguyên $a,b$ đều khác $0$, chúng ta có công thức:

$$
\boxed{
\gcd(a,b)\times\operatorname{lcm}(a,b)=|ab|
}
$$

Từ đó, suy ra:

$$
\boxed{
\operatorname{lcm}(a,b)=
\frac{|ab|}{\gcd(a,b)}
}
$$

Ví dụ:

Cho:

$$
a=12,\qquad b=18.
$$

Chúng ta đã biết:

$$
\gcd(12,18)=6.
$$

Do đó:

$$
\operatorname{lcm}(12,18)
=
\frac{12\times18}{6}
$$

Suy ra:

$$
\boxed{\operatorname{lcm}(12,18)=36}
$$

Như vậy, khi đã tìm được UCLN, chúng ta có thể sử dụng công thức trên để tính BCNN mà không cần liệt kê toàn bộ các bội chung.

---

## 4. Thuật toán Euclid

### 4.1. Một cách tiếp cận khác để tìm UCLN

Thông thường, chúng ta có thể tìm UCLN bằng cách liệt kê tất cả các ước của hai số rồi tìm ước chung lớn nhất.

Ví dụ, để tìm:

$$
\gcd(12,18),
$$

chúng ta liệt kê các ước dương của từng số và nhận thấy kết quả là $6$.

Tuy nhiên, phương pháp này trở nên bất tiện khi các số cần xét lớn.

Chẳng hạn, nếu cần tìm:

$$
\gcd(123456,78912),
$$

việc liệt kê toàn bộ các ước sẽ mất nhiều công sức.

Để giải quyết vấn đề này, chúng ta sử dụng một phương pháp toán học hiệu quả hơn: thuật toán Euclid.

### 4.2. Ý tưởng của thuật toán Euclid

Thuật toán Euclid dựa trên một tính chất quan trọng:

Nếu:

$$
a=bq+r,
$$

thì:

$$
\boxed{\gcd(a,b)=\gcd(b,r)}
$$

Trong đó:

$$
a,b,r\in\mathbb Z,\qquad 0\le r<b.
$$

Điều này có nghĩa là chúng ta có thể thay một cặp số bằng một cặp số nhỏ hơn mà không làm thay đổi UCLN.

### 4.3. Tại sao tính chất này đúng?

Giả sử $d$ là một ước chung của $a$ và $b$.

Điều đó có nghĩa là tồn tại các số nguyên $u,v$ sao cho:

$$
a=du,\qquad b=dv.
$$

Vì:

$$
r=a-bq,
$$

nên:

$$
r=du-dvq.
$$

Ta có thể đặt $d$ làm nhân tử chung:

$$
r=d(u-vq).
$$

Vì $u-vq$ là số nguyên, nên $d$ cũng là ước của $r$.

Như vậy, mọi ước chung của $a,b$ đều là ước chung của $b,r$.

Chiều ngược lại cũng đúng.

Nếu $d$ là ước chung của $b,r$, thì từ:

$$
a=bq+r
$$

suy ra $d$ cũng là ước của $a$.

Do đó, hai cặp $(a,b)$ và $(b,r)$ có cùng các ước chung.

Vì vậy:

$$
\boxed{\gcd(a,b)=\gcd(b,r)}
$$

Đây chính là cơ sở toán học của thuật toán Euclid.

### 4.4. Ví dụ: Tìm UCLN của $114$ và $51$

Chúng ta bắt đầu bằng phép chia:

$$
114=2\times51+12.
$$

Theo tính chất vừa chứng minh:

$$
\gcd(114,51)=\gcd(51,12).
$$

Tiếp tục chia:

$$
51=4\times12+3.
$$

Suy ra:

$$
\gcd(51,12)=\gcd(12,3).
$$

Cuối cùng:

$$
12=4\times3+0.
$$

Khi số dư bằng $0$, thuật toán dừng lại.

Ước chung lớn nhất chính là số dư khác $0$ cuối cùng.

Vậy:

$$
\boxed{\gcd(114,51)=3}
$$

Chúng ta có thể viết toàn bộ quá trình dưới dạng:

$$
\begin{aligned}
114&=2\times51+12,\\
51&=4\times12+3,\\
12&=4\times3+0.
\end{aligned}
$$

### 4.5. Tại sao thuật toán chắc chắn dừng lại?

Ở mỗi bước, chúng ta thực hiện phép chia có dư:

$$
a=bq+r
$$

với:

$$
0\le r<b.
$$

Điều này có nghĩa là số dư mới luôn nhỏ hơn số chia hiện tại.

Nếu số dư khác $0$, chúng ta tiếp tục thực hiện phép chia với cặp số mới.

Vì các số dư là những số nguyên không âm và giảm dần, quá trình này không thể tiếp tục vô hạn.

Cuối cùng, chúng ta sẽ nhận được một số dư bằng $0$.

Đây là lý do thuật toán Euclid luôn kết thúc sau một số hữu hạn bước.

### 4.6. Xử lý số nguyên âm

Thuật toán Euclid có thể áp dụng cho các số nguyên âm bằng cách lấy giá trị tuyệt đối của chúng trước khi thực hiện.

Ví dụ:

$$
\gcd(-114,125)
=
\gcd(114,125).
$$

Sau đó, chúng ta thực hiện thuật toán trên hai số dương.

Kết quả UCLN luôn không âm, vì vậy dấu của các số ban đầu không ảnh hưởng đến giá trị UCLN.

---

## 5. Bổ đề Bézout

### 5.1. Tổ hợp tuyến tính là gì?

Trong đại số, một biểu thức có dạng:

$$
ax+by
$$

được gọi là tổ hợp tuyến tính của $a,b$, trong đó $x,y$ là các hệ số.

Nếu $a,b,x,y$ đều là số nguyên, chúng ta gọi đây là một tổ hợp tuyến tính nguyên.

Ví dụ:

$$
2\times3+4\times5=26.
$$

Ở đây, $26$ là một tổ hợp tuyến tính nguyên của $3$ và $5$.

Một cặp số có thể có nhiều cách biểu diễn bằng tổ hợp tuyến tính khác nhau.

### 5.2. Phát biểu bổ đề Bézout

Bổ đề Bézout phát biểu rằng:

Với hai số nguyên $a,b$, không đồng thời bằng $0$, luôn tồn tại hai số nguyên $x,y$ sao cho:

$$
\boxed{ax+by=\gcd(a,b)}
$$

Hai số nguyên $x,y$ được gọi là các hệ số Bézout của $a,b$.

Ngoài ra, mọi tổ hợp tuyến tính nguyên của $a,b$ đều là bội của UCLN.

Nói cách khác, nếu:

$$
e=ax+by
$$

với $x,y\in\mathbb Z$, thì:

$$
\gcd(a,b)\mid e.
$$

Do đó, UCLN là số nguyên dương nhỏ nhất có thể biểu diễn dưới dạng một tổ hợp tuyến tính nguyên của hai số đã cho.

### 5.3. Ví dụ

Chúng ta đã tìm được:

$$
\gcd(114,51)=3.
$$

Bây giờ, nếu tìm được hai số nguyên $x,y$ sao cho:

$$
114x+51y=3,
$$

thì chúng ta đã tìm được một biểu diễn Bézout của hai số ban đầu.

Một cách biểu diễn là:

$$
3=(-4)\times114+9\times51.
$$

Vậy:

$$
\boxed{x=-4,\qquad y=9}
$$

### 5.4. Tại sao bổ đề Bézout quan trọng?

Bổ đề Bézout cho chúng ta một cách liên hệ giữa UCLN và các tổ hợp tuyến tính.

Điều này đặc biệt hữu ích khi chúng ta muốn tìm một số nguyên $x$ thỏa mãn:

$$
ax+my=1.
$$

Vì $my$ là một bội của $m$, khi xét theo modulo $m$, biểu thức trên trở thành:

$$
ax\equiv1\pmod m.
$$

Đây chính là định nghĩa của nghịch đảo modulo.

Như vậy, nếu chúng ta tìm được các hệ số Bézout cho hai số có UCLN bằng $1$, chúng ta có thể sử dụng chúng để tìm nghịch đảo modulo.

Để thực hiện điều đó một cách có hệ thống, chúng ta cần đến thuật toán Euclid mở rộng.

---

## 6. Thuật toán Euclid mở rộng

### 6.1. Mục đích của thuật toán

Thuật toán Euclid thông thường giúp tìm:

$$
\gcd(a,b).
$$

Thuật toán Euclid mở rộng có thêm một mục tiêu:

Tìm hai số nguyên $x,y$ sao cho:

$$
\boxed{ax+by=\gcd(a,b)}
$$

Nói cách khác, thay vì chỉ biết UCLN bằng bao nhiêu, chúng ta còn muốn biết UCLN đó được tạo thành như thế nào từ hai số ban đầu.

### 6.2. Ý tưởng của thuật toán Euclid mở rộng

Thuật toán Euclid thông thường liên tục biến đổi một cặp số thành cặp số nhỏ hơn bằng phép chia có dư.

Điểm quan trọng là mỗi số dư đều có thể được biểu diễn theo hai số ban đầu.

Chẳng hạn:

$$
114=2\times51+12.
$$

Chuyển vế:

$$
12=114-2\times51.
$$

Như vậy, số dư $12$ đã được biểu diễn dưới dạng tổ hợp tuyến tính của $114$ và $51$.

Tiếp tục:

$$
51=4\times12+3.
$$

Chuyển vế:

$$
3=51-4\times12.
$$

Nếu thay biểu thức của $12$ vào, chúng ta có thể biểu diễn $3$ theo hai số ban đầu.

Đây chính là ý tưởng của thuật toán Euclid mở rộng: sau khi tìm được UCLN bằng thuật toán Euclid, chúng ta thực hiện phép thế ngược để khôi phục các hệ số tương ứng.

### 6.3. Ví dụ: Tìm hệ số Bézout của $114$ và $51$

Ở phần trước, chúng ta đã có:

$$
114=2\times51+12
$$

$$
51=4\times12+3
$$

$$
12=4\times3+0.
$$

Do đó:

$$
\gcd(114,51)=3.
$$

Bây giờ, chúng ta cần tìm hai số nguyên $x,y$ sao cho:

$$
114x+51y=3.
$$

Bắt đầu từ phương trình có số dư khác $0$ cuối cùng:

$$
3=51-4\times12.
$$

Từ phép chia đầu tiên:

$$
12=114-2\times51.
$$

Thay vào biểu thức ban đầu:

$$
3=51-4(114-2\times51).
$$

Khai triển:

$$
3=51-4\times114+8\times51.
$$

Gộp các hệ số của $51$:

$$
3=-4\times114+9\times51.
$$

Vậy:

$$
\boxed{3=(-4)\times114+9\times51}
$$

Hai hệ số Bézout cần tìm là:

$$
\boxed{x=-4,\qquad y=9}
$$

### 6.4. Kiểm tra kết quả

Để kiểm tra, chúng ta thay hai hệ số vừa tìm được vào biểu thức ban đầu:

$$
(-4)\times114+9\times51.
$$

Ta có:

$$
-456+459=3.
$$

Kết quả đúng bằng:

$$
\gcd(114,51)=3.
$$

Vì vậy, cặp hệ số Bézout đã tìm được là chính xác.

### 6.5. Ví dụ với số nguyên âm

Cho:

$$
a=-114,\qquad b=125.
$$

Yêu cầu:

1. Tìm UCLN và BCNN.
2. Tìm hai số nguyên $x,y$ sao cho:

$$
ax+by=\gcd(a,b).
$$

3. Kiểm tra xem hệ số $x$ có phải là nghịch đảo modulo của $a$ theo modulo $b$ hay không.

**Bước 1. Tìm UCLN**

Vì dấu của số nguyên không làm thay đổi UCLN:

$$
\gcd(-114,125)=\gcd(114,125)
$$

Áp dụng thuật toán Euclid:

$$
125=1\times114+11
$$

$$
114=10\times11+4
$$

$$
11=2\times4+3
$$

$$
4=1\times3+1
$$

$$
3=3\times1+0.
$$

Số dư khác $0$ cuối cùng là $1$

Do đó:

$$
\boxed{\gcd(-114,125)=1}
$$

**Bước 2. Tìm BCNN**

Sử dụng công thức:

$$
\operatorname{lcm}(a,b)=\frac{|ab|}{\gcd(a,b)}
$$

Ta có:

$$
\operatorname{lcm}(-114,125)
=
\frac{|-114\times125|}{1}
$$

Vậy:

$$
\boxed{\operatorname{lcm}(-114,125)=14250}
$$

**Bước 3. Tìm các hệ số Bézout**

Bắt đầu từ phép chia có số dư khác $0$ cuối cùng:

$$
1=4-3.
$$

Vì:

$$
3=11-2\times4,
$$

nên:

$$
1=4-(11-2\times4).
$$

Suy ra:

$$
1=3\times4-11.
$$

Tiếp tục thay:

$$
4=114-10\times11.
$$

Ta được:

$$
1=3(114-10\times11)-11.
$$

Khai triển:

$$
1=3\times114-31\times11.
$$

Mặt khác:

$$
11=125-114.
$$

Thay vào:

$$
1=3\times114-31(125-114).
$$

Khai triển và thu gọn:

$$
1=34\times114-31\times125.
$$

Tuy nhiên, số nguyên ban đầu là $-114$, không phải $114$.

Vì:

$$
114=-(-114),
$$

nên:

$$
\boxed{
1=(-34)\times(-114)+(-31)\times125
}
$$

Vậy hai hệ số Bézout tương ứng là:

$$
\boxed{x=-34,\qquad y=-31}
$$

**Bước 4. Kiểm tra kết quả**

Thay vào:

$$
(-34)\times(-114)+(-31)\times125.
$$

Ta có:

$$
3876-3875=1.
$$

Kết quả chính xác.

Như vậy, chúng ta đã tìm được một biểu diễn Bézout của hai số nguyên ban đầu.

---

## 7. Nghịch đảo modulo

### 7.1. Nghịch đảo trong đại số thông thường

Trong đại số, nghịch đảo nhân của một số $a\ne0$ là một số $a^{-1}$ thỏa mãn:

$$
a\times a^{-1}=1.
$$

Ví dụ:

$$
2^{-1}=\frac12
$$

vì:

$$
2\times\frac12=1.
$$

Tuy nhiên, trong tập hợp số nguyên $\mathbb Z$, không phải mọi số đều có nghịch đảo nhân.

Chẳng hạn, không tồn tại số nguyên $x$ sao cho:

$$
2x=1.
$$

Bởi vì kết quả của $2x$ luôn là một số chẵn, không thể bằng $1$.

Trong modulo, chúng ta có một khái niệm tương tự nhưng có cách xác định riêng.

### 7.2. Định nghĩa nghịch đảo modulo

Cho một số nguyên $a$ và một số nguyên $m>1$.

Một số nguyên $x$ được gọi là nghịch đảo modulo của $a$ theo modulo $m$ nếu:

$$
\boxed{ax\equiv1\pmod m}
$$

Nếu nghịch đảo tồn tại, chúng ta ký hiệu:

$$
\boxed{x\equiv a^{-1}\pmod m}
$$

Nói cách khác:

$$
\boxed{a\times a^{-1}\equiv1\pmod m}
$$

Cần chú ý rằng $a^{-1}$ trong biểu thức trên là nghịch đảo modulo, không nhất thiết là nghịch đảo trong phép toán thông thường.

### 7.3. Ví dụ tìm nghịch đảo modulo

Tìm nghịch đảo modulo của $3$ theo modulo $7$.

Chúng ta cần tìm một số nguyên $x$ sao cho:

$$
3x\equiv1\pmod7.
$$

Thử một số giá trị:

Với $x=1$:

$$
3\times1=3.
$$

Không thỏa mãn.

Với $x=2$:

$$
3\times2=6.
$$

Không thỏa mãn.

Với $x=5$:

$$
3\times5=15.
$$

Vì:

$$
15=7\times2+1,
$$

nên:

$$
3\times5\equiv1\pmod7.
$$

Do đó:

$$
\boxed{3^{-1}\equiv5\pmod7}
$$

### 7.4. Điều kiện tồn tại nghịch đảo modulo

Đây là một trong những kết quả quan trọng nhất của bài học.

Cho hai số nguyên $a,m$, với $m>1$.

Nghịch đảo modulo của $a$ theo modulo $m$ tồn tại khi và chỉ khi:

$$
\boxed{\gcd(a,m)=1}
$$

Điều này có nghĩa là hai số $a,m$ phải có ước chung lớn nhất bằng $1$.

Chẳng hạn:

$$
\gcd(3,7)=1.
$$

Do đó, $3$ có nghịch đảo modulo $7$.

Ngược lại:

$$
\gcd(2,6)=2.
$$

Vì vậy, $2$ không có nghịch đảo modulo $6$.

### 7.5. Tại sao điều kiện UCLN bằng $1$ lại quan trọng?

Chúng ta sẽ giải thích cả hai chiều của kết quả này.

**Chiều thứ nhất: Nếu nghịch đảo tồn tại thì UCLN bằng $1$.**

Giả sử tồn tại số nguyên $x$ sao cho:

$$
ax\equiv1\pmod m.
$$

Theo định nghĩa đồng dư, tồn tại một số nguyên $y$ sao cho:

$$
ax-my=1.
$$

Như vậy, $1$ có thể được biểu diễn thành một tổ hợp tuyến tính nguyên của $a$ và $m$.

Mọi ước chung của $a$ và $m$ đều phải là ước của $1$.

Số nguyên dương duy nhất chia hết $1$ là $1$.

Do đó:

$$
\gcd(a,m)=1.
$$

**Chiều thứ hai: Nếu UCLN bằng $1$ thì nghịch đảo tồn tại.**

Giả sử:

$$
\gcd(a,m)=1.
$$

Theo bổ đề Bézout, tồn tại hai số nguyên $x,y$ sao cho:

$$
ax+my=1.
$$

Xét modulo $m$, chúng ta có:

$$
ax+my\equiv1\pmod m.
$$

Vì $my$ chia hết cho $m$, nên:

$$
ax\equiv1\pmod m.
$$

Do đó, $x$ chính là nghịch đảo modulo của $a$.

Vậy chúng ta đã chứng minh được:

$$
\boxed{
a^{-1}\pmod m\text{ tồn tại}
\iff
\gcd(a,m)=1
}
$$

### 7.6. Tìm nghịch đảo modulo bằng thuật toán Euclid mở rộng

Chúng ta đã biết thuật toán Euclid mở rộng có thể tìm hai số nguyên $x,y$ sao cho:

$$
ax+my=\gcd(a,m).
$$

Nếu:

$$
\gcd(a,m)=1,
$$

thì:

$$
ax+my=1.
$$

Xét modulo $m$:

$$
ax\equiv1\pmod m.
$$

Do đó:

$$
\boxed{x\equiv a^{-1}\pmod m}
$$

Như vậy, hệ số của $a$ trong biểu diễn Bézout chính là nghịch đảo modulo cần tìm.

Ví dụ, ta đã có:

$$
1=34\times114-31\times125.
$$

Xét modulo $125$:

$$
34\times114\equiv1\pmod{125}
$$

Vậy:

$$
\boxed{114^{-1}\equiv34\pmod{125}}
$$

Nếu xét số $-114$, biểu diễn Bézout tương ứng là:

$$
1=(-34)\times(-114)+(-31)\times125.
$$

Do đó:

$$
\boxed{(-114)^{-1}\equiv-34\pmod{125}}
$$

Kiểm tra:

$$
(-114)\times(-34)=3876.
$$

Vì:

$$
3876=125\times31+1,
$$

nên:

$$
3876\equiv1\pmod{125}
$$

Kết quả hoàn toàn chính xác.

**Lưu ý:** Nghịch đảo modulo không phải là một số nguyên duy nhất. Chẳng hạn, $-34$, $91$ và $216$ đều biểu diễn cùng một lớp đồng dư modulo $125$.

### 7.7. Giải phương trình modulo bằng nghịch đảo

Bây giờ, chúng ta có thể quay lại phương trình:

$$
ax\equiv b\pmod m.
$$

Nếu:

$$
\gcd(a,m)=1,
$$

thì nghịch đảo modulo của $a$ tồn tại.

Nhân cả hai vế với $a^{-1}$:

$$
a^{-1}ax\equiv a^{-1}b\pmod m.
$$

Vì:

$$
a^{-1}a\equiv1\pmod m,
$$

nên:

$$
\boxed{x\equiv a^{-1}b\pmod m}
$$

Ví dụ:

Giải phương trình:

$$
3x\equiv2\pmod7.
$$

Chúng ta đã biết:

$$
3^{-1}\equiv5\pmod7.
$$

Do đó:

$$
x\equiv5\times2\pmod7.
$$

Suy ra:

$$
\boxed{x\equiv3\pmod7}
$$

Kiểm tra:

$$
3\times3=9\equiv2\pmod7.
$$

Phương trình được thỏa mãn.

### 7.8. Trường hợp nghịch đảo không tồn tại

Một câu hỏi quan trọng là: nếu:

$$
\gcd(a,m)\ne1,
$$

thì phương trình:

$$
ax\equiv b\pmod m
$$

có còn nghiệm hay không?

Câu trả lời là có thể có hoặc không.

Đặt:

$$
d=\gcd(a,m).
$$

Phương trình có nghiệm khi và chỉ khi:

$$
\boxed{d\mid b}
$$

Nói cách khác, UCLN của hệ số và modulo phải chia hết số ở vế phải.

Nếu điều kiện này không thỏa mãn, phương trình không có nghiệm.

Nếu điều kiện này thỏa mãn, phương trình có đúng $d$ lớp nghiệm khác nhau modulo $m$.

**Ví dụ thứ nhất: Phương trình có nghiệm**

Xét:

$$
6x\equiv8\pmod{14}
$$

Ta có:

$$
\gcd(6,14)=2.
$$

Vì:

$$
2\mid8,
$$

nên phương trình có nghiệm.

Chia cả ba hệ số của phương trình cho $2$, chúng ta được:

$$
3x\equiv4\pmod7.
$$

Vì:

$$
\gcd(3,7)=1,
$$

nghịch đảo modulo tồn tại.

Ta đã biết:

$$
3^{-1}\equiv5\pmod7.
$$

Do đó:

$$
x\equiv5\times4\pmod7.
$$

Suy ra:

$$
x\equiv20\equiv6\pmod7.
$$

Tuy nhiên, cần chú ý rằng phương trình ban đầu có modulo $14$, không phải modulo $7$.

Vì vậy, khi biểu diễn nghiệm theo modulo $14$, chúng ta có hai lớp nghiệm:

$$
\boxed{x\equiv6\pmod{14}}
$$

hoặc:

$$
\boxed{x\equiv13\pmod{14}}
$$

Kiểm tra:

Với $x=6$:

$$
6\times6=36\equiv8\pmod{14}
$$

Với $x=13$:

$$
6\times13=78\equiv8\pmod{14}
$$

Cả hai đều là nghiệm.

**Ví dụ thứ hai: Phương trình không có nghiệm**

Xét:

$$
6x\equiv5\pmod{14}
$$

Ta có:

$$
\gcd(6,14)=2.
$$

Nhưng:

$$
2\nmid5.
$$

Vì vậy, phương trình không có nghiệm.

Kết quả này cho thấy không phải mọi phương trình modulo đều giải được bằng cách sử dụng nghịch đảo modulo. Chúng ta luôn cần kiểm tra điều kiện tồn tại nghiệm trước.

---

## 8. Định lý nhỏ Fermat

### 8.1. Số nguyên tố là gì?

Một số nguyên dương $p>1$ được gọi là số nguyên tố nếu nó chỉ có đúng hai ước dương:

$$
1\quad\text{và}\quad p.
$$

Ví dụ:

$$
2,3,5,7,11,13,17
$$

đều là các số nguyên tố.

Ngược lại, số $6$ không phải số nguyên tố vì nó có các ước dương:

$$
1,2,3,6.
$$

Những số nguyên dương lớn hơn $1$ nhưng không phải số nguyên tố được gọi là hợp số.

### 8.2. Phát biểu định lý nhỏ Fermat

Định lý nhỏ Fermat là một kết quả quan trọng trong lý thuyết số.

Định lý phát biểu rằng:

Nếu $p$ là số nguyên tố và $a$ là một số nguyên bất kỳ thì:

$$
\boxed{a^p\equiv a\pmod p}
$$

Một dạng tương đương của định lý là:

Nếu $p$ là số nguyên tố và:

$$
p\nmid a,
$$

thì:

$$
\boxed{a^{p-1}\equiv1\pmod p}
$$

Ở đây:

- $p$ là số nguyên tố.
- $a$ là số nguyên.
- $p\nmid a$ có nghĩa là $p$ không chia hết $a$.

Điều kiện $p\nmid a$ rất quan trọng đối với dạng thứ hai của định lý.

### 8.3. Ví dụ

Cho:

$$
a=2,\qquad p=5.
$$

Vì $5$ là số nguyên tố và $5$ không chia hết $2$, theo định lý nhỏ Fermat:

$$
2^{5-1}\equiv1\pmod5.
$$

Ta có:

$$
2^4=16.
$$

Mà:

$$
16\bmod5=1.
$$

Do đó:

$$
\boxed{2^4\equiv1\pmod5}
$$

### 8.4. Mối liên hệ với nghịch đảo modulo

Định lý nhỏ Fermat còn cung cấp một phương pháp để tìm nghịch đảo modulo.

Giả sử:

- $p$ là số nguyên tố.
- $p\nmid a$.

Theo định lý nhỏ Fermat:

$$
a^{p-1}\equiv1\pmod p.
$$

Chúng ta có thể viết lại:

$$
a\times a^{p-2}\equiv1\pmod p.
$$

Theo định nghĩa nghịch đảo modulo:

$$
\boxed{a^{-1}\equiv a^{p-2}\pmod p}
$$

Ví dụ, tìm nghịch đảo modulo của $3$ theo modulo $7$.

Theo định lý nhỏ Fermat:

$$
3^{-1}\equiv3^{7-2}\pmod7.
$$

Suy ra:

$$
3^{-1}\equiv3^5\pmod7.
$$

Ta có:

$$
3^5=243.
$$

Vì:

$$
243=7\times34+5,
$$

nên:

$$
\boxed{3^{-1}\equiv5\pmod7}
$$

Kết quả này trùng với kết quả chúng ta đã tìm được bằng phép thử ở phần trước.

### 8.5. Sử dụng định lý nhỏ Fermat để rút gọn số mũ

Một ứng dụng khác của định lý nhỏ Fermat là tính những lũy thừa có số mũ rất lớn.

Ví dụ, hãy tính:

$$
3^{100}\bmod7.
$$

Vì $7$ là số nguyên tố và $7\nmid3$, theo định lý nhỏ Fermat:

$$
3^6\equiv1\pmod7.
$$

Chúng ta có thể phân tích số mũ:

$$
100=6\times16+4.
$$

Do đó:

$$
3^{100}
=
(3^6)^{16}\times3^4.
$$

Xét modulo $7$:

$$
3^{100}\equiv1^{16}\times3^4\pmod7.
$$

Suy ra:

$$
3^{100}\equiv3^4\pmod7.
$$

Ta có:

$$
3^4=81.
$$

Và:

$$
81\bmod7=4.
$$

Vậy:

$$
\boxed{3^{100}\equiv4\pmod7}
$$

Thay vì tính trực tiếp $3^{100}$, chúng ta chỉ cần tính một lũy thừa nhỏ hơn rất nhiều.

### 8.6. Phân biệt Euclid mở rộng và định lý nhỏ Fermat

Chúng ta đã biết hai phương pháp tìm nghịch đảo modulo.

**Phương pháp thứ nhất: Thuật toán Euclid mở rộng**

Điều kiện:

$$
\gcd(a,m)=1.
$$

Phương pháp này có thể được sử dụng với cả modulo là số nguyên tố và modulo là hợp số.

**Phương pháp thứ hai: Định lý nhỏ Fermat**

Điều kiện:

- Modulo $p$ phải là số nguyên tố.
- $p$ không chia hết $a$.

Khi đó:

$$
\boxed{a^{-1}\equiv a^{p-2}\pmod p}
$$

Hai phương pháp đều tìm được nghịch đảo modulo, nhưng phạm vi áp dụng khác nhau.

Đặc biệt, định lý nhỏ Fermat không thể được áp dụng tùy ý khi modulo là hợp số.

---

# Bài tập về nhà — 7 bài từ cơ bản đến nâng cao

Các bài tập được sắp xếp theo mức độ tăng dần.

Mục tiêu không chỉ là tìm ra kết quả đúng, mà còn là hiểu tại sao phương pháp giải có thể được sử dụng và những điều kiện nào cần được thỏa mãn.

Đối với các bài sử dụng thuật toán Euclid hoặc thuật toán Euclid mở rộng, hãy trình bày đầy đủ các phép chia có dư và những bước biến đổi cần thiết.

## Mức 1 — Vận dụng đồng dư và phương trình modulo

### Bài 1. Phương trình đồng dư tuyến tính

Giải các phương trình sau:

a.

$$
x+17\equiv5\pmod{12}
$$

b.

$$
23-x\equiv8\pmod{11}
$$

c.

$$
x-(-7)\equiv13\pmod9
$$

d.

$$
x+2026\equiv-15\pmod{17}
$$

Với mỗi phương trình, hãy:

1. Biến đổi phương trình để cô lập biến $x$.
2. Tìm một nghiệm đại diện có giá trị nằm trong khoảng từ $0$ đến $m-1$.
3. Viết nghiệm tổng quát.
4. Kiểm tra ít nhất một nghiệm bằng cách thay trực tiếp vào phương trình ban đầu.

## Mức 2 — Điều kiện tồn tại nghịch đảo modulo

### Bài 2. Nghịch đảo modulo và điều kiện tồn tại

Xét các số sau:

$$
(a,m)=(8,15),\quad(12,35),\quad(21,49),\quad(37,101).
$$

Với mỗi cặp, hãy:

a. Tính:

$$
\gcd(a,m).
$$

b. Xác định nghịch đảo modulo của $a$ theo modulo $m$ có tồn tại hay không.

c. Nếu tồn tại, hãy tìm nghịch đảo bằng cách giải phương trình:

$$
ax\equiv1\pmod m.
$$

d. Kiểm tra kết quả bằng phép nhân modulo.

e. Giải thích tại sao những trường hợp có UCLN khác $1$ không thể có nghịch đảo modulo.

Bài này yêu cầu phân biệt rõ giữa việc một phép chia có thể thực hiện trong đại số thông thường và việc một nghịch đảo có tồn tại trong modulo.

## Mức 3 — Thuật toán Euclid và BCNN

### Bài 3. Tìm UCLN và BCNN bằng thuật toán Euclid

Cho hai số nguyên:

$$
a=-2520,\qquad b=1980.
$$

Hãy thực hiện các yêu cầu sau:

a. Giải thích tại sao có thể sử dụng giá trị tuyệt đối để thực hiện thuật toán Euclid.

b. Sử dụng thuật toán Euclid để tìm:

$$
d=\gcd(a,b).
$$

c. Từ kết quả trên, tìm:

$$
e=\operatorname{lcm}(a,b).
$$

d. Kiểm tra mối quan hệ:

$$
d\times e=|ab|.
$$

e. Giải thích tại sao thuật toán Euclid có thể tìm được UCLN mà không cần liệt kê toàn bộ các ước chung của hai số.

## Mức 4 — Biểu diễn tuyến tính và thuật toán Euclid mở rộng

### Bài 4. Tìm các hệ số Bézout

Cho:

$$
a=2520,\qquad b=1980.
$$

Yêu cầu tìm hai số nguyên $x,y$ sao cho:

$$
\gcd(a,b)=ax+by.
$$

Hãy thực hiện:

a. Tìm UCLN bằng thuật toán Euclid.

b. Viết lại từng phương trình chia có dư để biểu diễn số dư theo các số đứng trước.

c. Thực hiện phép thế ngược để đưa UCLN về dạng tổ hợp tuyến tính của hai số ban đầu.

d. Xác định các hệ số Bézout $x,y$.

e. Kiểm tra kết quả bằng cách thay trực tiếp hai hệ số vào biểu thức ban đầu.

f. Tìm một cặp hệ số Bézout khác với cặp vừa tìm được. Giải thích vì sao hai cặp hệ số khác nhau vẫn có thể biểu diễn cùng một UCLN.

## Mức 5 — Ứng dụng nghịch đảo modulo

### Bài 5. Giải phương trình modulo bằng thuật toán Euclid mở rộng

Cho phương trình:

$$
35x\equiv12\pmod{64}
$$

Hãy giải phương trình bằng cách sử dụng thuật toán Euclid mở rộng.

Yêu cầu:

a. Tính:

$$
\gcd(35,64).
$$

b. Xác định nghịch đảo modulo của $35$ theo modulo $64$ có tồn tại hay không.

c. Sử dụng thuật toán Euclid mở rộng để tìm các hệ số Bézout.

d. Từ biểu diễn Bézout, xác định:

$$
35^{-1}\pmod{64}
$$

e. Sử dụng nghịch đảo modulo để tìm nghiệm của phương trình ban đầu.

f. Kiểm tra nghiệm bằng cách thay lại vào phương trình.

g. Viết tất cả nghiệm nguyên dưới dạng tổng quát.

## Mức 6 — Định lý nhỏ Fermat và lũy thừa modulo

### Bài 6. Khai thác định lý nhỏ Fermat

Cho số nguyên tố:

$$
p=13.
$$

a. Sử dụng định lý nhỏ Fermat để xác định:

$$
2^{2026}\bmod13.
$$

b. Tính:

$$
7^{2026}\bmod13.
$$

c. Tìm nghịch đảo modulo của $5$ theo modulo $13$ bằng định lý nhỏ Fermat.

d. Kiểm tra kết quả ở câu c bằng cách sử dụng thuật toán Euclid mở rộng.

e. Giải thích tại sao chúng ta có thể rút gọn số mũ khi tính một lũy thừa modulo trong điều kiện áp dụng định lý nhỏ Fermat.

Không cần tính trực tiếp giá trị nguyên của những lũy thừa rất lớn.

## Mức 7 — Bài toán tổng hợp: Giải phương trình đồng dư tổng quát

### Bài 7. Phân tích và giải phương trình đồng dư

Cho phương trình:

$$
84x\equiv30\pmod{198}
$$

Đây là một phương trình không thể giải trực tiếp bằng cách lấy nghịch đảo modulo của $84$, vì:

$$
\gcd(84,198)\ne1.
$$

Hãy thực hiện các yêu cầu sau:

a. Tính:

$$
d=\gcd(84,198)
$$

bằng thuật toán Euclid.

b. Kiểm tra điều kiện tồn tại nghiệm của phương trình.

c. Rút gọn phương trình bằng cách chia hệ số và modulo cho $d$.

d. Sử dụng thuật toán Euclid mở rộng để tìm nghịch đảo modulo của hệ số mới sau khi rút gọn.

e. Tìm một lớp nghiệm của phương trình đã rút gọn.

f. Suy ra tất cả các lớp nghiệm khác nhau của phương trình ban đầu theo modulo $198$.

g. Kiểm tra từng nghiệm bằng cách thay vào phương trình ban đầu.

**Thử thách bổ sung:**

Hãy chứng minh rằng nếu:

$$
ax\equiv b\pmod m
$$

với:

$$
d=\gcd(a,m),
$$

thì:

- Phương trình không có nghiệm nếu $d$ không chia hết $b$.
- Phương trình có đúng $d$ lớp nghiệm khác nhau modulo $m$ nếu $d$ chia hết $b$.

Chứng minh của bạn cần sử dụng định nghĩa đồng dư và thuật toán Euclid hoặc bổ đề Bézout. Không được chỉ viện dẫn lại kết luận của bài học.
