# Tuần 1 — Số nguyên và phép toán modulo

## Mục tiêu bài học

Trong tuần này, chúng ta sẽ xây dựng nền tảng về số nguyên và phép toán modulo.

Sau khi hoàn thành bài học, người đọc cần có khả năng:

1. Hiểu các tập hợp số cơ bản và mối quan hệ giữa chúng.
2. Vận dụng các tính chất đại số của số nguyên.
3. Hiểu định lý chia có dư và tính duy nhất của thương nguyên, số dư.
4. Tính modulo với cả số nguyên dương và số nguyên âm.
5. Sử dụng những tính chất cơ bản của modulo để rút gọn các biểu thức.
6. Hiểu và chứng minh các tính chất chẵn lẻ bằng lập luận toán học.

Bài học này tập trung vào số nguyên và phép toán modulo. Các nội dung về số nguyên tố, ước số, bội số và những tính chất chia hết sẽ được phát triển trong tuần 3.

---

## 1. Các thế giới toán học

### 1.1. Toán học được xây dựng như thế nào?

Trong quá trình học toán, chúng ta thường gặp nhiều lĩnh vực khác nhau. Một số lĩnh vực quen thuộc ở bậc phổ thông là đại số, hình học Euclid và lượng giác.

Mỗi lĩnh vực có những đối tượng, quy tắc và phương pháp giải quyết vấn đề riêng.

Chẳng hạn:

- Hình học nghiên cứu các đối tượng như điểm, đường thẳng, đường tròn và tam giác.
- Đại số nghiên cứu các biểu thức, số, biến và những quan hệ toán học.
- Lượng giác nghiên cứu các mối quan hệ giữa góc và những đại lượng liên quan.

Vậy làm thế nào để chúng ta có thể xây dựng một lĩnh vực toán học mới?

Hãy tưởng tượng toán học giống như một bức tường được xây dựng từ những viên gạch. Những viên gạch ở dưới cùng đại diện cho các định nghĩa và tính chất cơ bản. Từ đó, chúng ta sử dụng những điều đã biết để xây dựng các kết quả phức tạp hơn.

Trong toán học, quá trình này thường diễn ra theo ba bước:

1. **Định nghĩa:** Xác định chính xác đối tượng mà chúng ta muốn nghiên cứu.
2. **Tính chất:** Xác định những quy tắc đúng với các đối tượng đó.
3. **Chứng minh:** Giải thích tại sao một kết luận nhất định phải đúng dựa trên những điều đã biết.

Ví dụ, thay vì chỉ nói rằng tổng của hai số chẵn luôn là số chẵn, chúng ta có thể sử dụng định nghĩa của số chẵn để chứng minh kết luận đó.

Điều quan trọng là toán học không chỉ yêu cầu chúng ta biết một kết quả, mà còn khuyến khích chúng ta hiểu kết quả đó có ý nghĩa gì, tại sao nó đúng và có thể được sử dụng trong những trường hợp nào.

Hình ảnh bức tường chỉ là một cách để hình dung quá trình xây dựng kiến thức. Trên thực tế, các ngành toán học có thể sử dụng những nền tảng và hệ tiên đề khác nhau.

### 1.2. Tại sao chúng ta học số nguyên?

Trong bài học này, chúng ta sẽ tập trung vào một đối tượng quan trọng của toán học: số nguyên.

Số nguyên xuất hiện trong rất nhiều tình huống:

- Nhiệt độ có thể thấp hơn $0^\circ\mathrm C$.
- Một tài khoản có thể có số dư âm.
- Độ cao của một vị trí có thể được biểu diễn bằng số âm nếu vị trí đó nằm dưới một mốc tham chiếu.
- Khi di chuyển trên một trục số, chúng ta có thể đi theo cả hai hướng.

Các số tự nhiên thông thường không đủ để biểu diễn tất cả những tình huống này.

Vì vậy, chúng ta cần một tập hợp số rộng hơn: tập hợp số nguyên.

Trong toán học, việc nghiên cứu những tính chất của các số nguyên thuộc một lĩnh vực gọi là **lý thuyết số**.

Đây là một lĩnh vực có nhiều nội dung khác nhau. Trong chương đầu tiên này, chúng ta sẽ bắt đầu với những kiến thức cơ bản nhất về số nguyên và phép toán modulo.

---

## 2. Số nguyên — Một tập hợp số quen thuộc

### 2.1. Tập hợp số tự nhiên

Trước tiên, hãy nhìn vào các số mà chúng ta đã biết:

$$
0,\ 1,\ 2,\ 3,\ 4,\ 5,\ldots
$$

Đây là các số tự nhiên.

Tập hợp số tự nhiên được ký hiệu là:

$$
\mathbb N.
$$

Trong tài liệu này, chúng ta sử dụng quy ước:

$$
\boxed{\mathbb N=\{0,1,2,3,\ldots\}}
$$

Điều đó có nghĩa là số $0$ cũng thuộc tập hợp số tự nhiên.

**Lưu ý:** Một số tài liệu sử dụng ký hiệu $\mathbb N$ cho tập hợp chỉ gồm các số nguyên dương. Vì vậy, quy ước về số $0$ cần được xác định rõ trong từng tài liệu.

### 2.2. Tập hợp số nguyên

Tập hợp số tự nhiên chỉ chứa số $0$ và các số dương.

Tuy nhiên, chúng ta còn cần những số âm như:

$$
-1,\ -2,\ -3,\ldots
$$

Khi bổ sung các số âm vào tập hợp số tự nhiên, chúng ta nhận được tập hợp số nguyên.

Tập hợp số nguyên được ký hiệu là:

$$
\mathbb Z.
$$

Ta có:

$$
\boxed{
\mathbb Z=\{\ldots,-3,-2,-1,0,1,2,3,\ldots\}
}
$$

Tập hợp số nguyên bao gồm ba nhóm:

- Số nguyên âm: $-1,-2,-3,\ldots$
- Số $0$.
- Số nguyên dương: $1,2,3,\ldots$

Ví dụ:

$$
-15,\quad -3,\quad 0,\quad 7,\quad125
$$

đều là các số nguyên.

Ngược lại:

$$
\frac12,\quad-\frac34,\quad2.5
$$

không phải là số nguyên.

### 2.3. Tập hợp số hữu tỉ

Trong quá trình thực hiện phép chia, chúng ta có thể nhận được những kết quả không phải số nguyên.

Ví dụ:

$$
5\div2=\frac52=2.5.
$$

Kết quả này không thuộc tập hợp số nguyên.

Để biểu diễn những số như vậy, chúng ta sử dụng tập hợp số hữu tỉ.

Tập hợp số hữu tỉ được ký hiệu là:

$$
\mathbb Q.
$$

Một số được gọi là số hữu tỉ nếu nó có thể biểu diễn dưới dạng:

$$
\frac pq
$$

trong đó:

$$
p,q\in\mathbb Z,\qquad q\ne0.
$$

Ví dụ:

$$
\frac12,\quad-\frac34,\quad\frac53,\quad5
$$

đều là các số hữu tỉ.

Cần chú ý rằng mọi số nguyên đều là số hữu tỉ, vì một số nguyên bất kỳ $a$ đều có thể biểu diễn dưới dạng:

$$
a=\frac a1.
$$

### 2.4. Tập hợp số thực

Tập hợp số thực được ký hiệu là:

$$
\mathbb R.
$$

Số thực bao gồm cả số hữu tỉ và những số không thể biểu diễn dưới dạng phân số của hai số nguyên.

Ví dụ:

$$
\sqrt2,\quad\pi,\quad-3,\quad\frac12
$$

đều là số thực.

Mối quan hệ giữa các tập hợp số mà chúng ta vừa tìm hiểu được biểu diễn như sau:

$$
\boxed{
\mathbb N\subseteq\mathbb Z
\subseteq\mathbb Q
\subseteq\mathbb R
}
$$

Ký hiệu $\subseteq$ có nghĩa là tập hợp ở bên trái nằm trong tập hợp ở bên phải.

Điều này có nghĩa là:

- Mọi số tự nhiên đều là số nguyên.
- Mọi số nguyên đều là số hữu tỉ.
- Mọi số hữu tỉ đều là số thực.

Tuy nhiên, điều ngược lại không nhất thiết đúng.

Ví dụ:

$$
\frac12\in\mathbb Q
$$

nhưng:

$$
\frac12\notin\mathbb Z.
$$

### 2.5. Giá trị tuyệt đối

Giá trị tuyệt đối của một số nguyên là khoảng cách từ số đó đến số $0$ trên trục số.

Ký hiệu giá trị tuyệt đối của $a$ là:

$$
|a|.
$$

Ví dụ:

$$
|5|=5,\qquad|-5|=5.
$$

Hai số $5$ và $-5$ có cùng khoảng cách đến $0$, mặc dù chúng nằm ở hai phía khác nhau trên trục số.

Tổng quát:

$$
\boxed{
|a|=
\begin{cases}
a,&a\ge0,\\
-a,&a<0.
\end{cases}
}
$$

Giá trị tuyệt đối luôn không âm:

$$
\boxed{|a|\ge0}.
$$

Khái niệm này sẽ hữu ích khi chúng ta thực hiện phép toán modulo với số âm.

---

## 3. Những tính chất cơ bản của phép toán

Trước khi học một phép toán mới, chúng ta cần hiểu các quy tắc cơ bản của những phép toán đã biết.

Trong phần này, giả sử $a,b,c$ là các số nguyên.

### 3.1. Tính chất giao hoán

Tính chất giao hoán cho biết rằng khi đổi vị trí hai số trong phép cộng hoặc phép nhân, kết quả không thay đổi.

Đối với phép cộng:

$$
\boxed{a+b=b+a}
$$

Đối với phép nhân:

$$
\boxed{a\times b=b\times a}
$$

Tuy nhiên, phép trừ không có tính chất giao hoán.

Chẳng hạn:

$$
5-3=2,\qquad3-5=-2.
$$

### 3.2. Tính chất kết hợp

Tính chất kết hợp cho biết rằng khi cộng hoặc nhân ba số, cách nhóm các số không làm thay đổi kết quả.

Đối với phép cộng:

$$
\boxed{(a+b)+c=a+(b+c)}
$$

Đối với phép nhân:

$$
\boxed{(a\times b)\times c=a\times(b\times c)}
$$

Tính chất này khác với tính chất giao hoán:

- Giao hoán nói về việc đổi vị trí các số.
- Kết hợp nói về việc thay đổi cách nhóm các số.

Phép trừ và phép chia không có tính chất kết hợp nói chung.

### 3.3. Tính chất phân phối

Tính chất phân phối liên kết phép nhân với phép cộng:

$$
\boxed{a(b+c)=ab+ac}
$$

Tương tự:

$$
\boxed{a(b-c)=ab-ac}
$$

Ví dụ:

$$
3(4+2)=3\times4+3\times2=18.
$$

Tính chất này giúp chúng ta biến đổi một biểu thức phức tạp thành những biểu thức đơn giản hơn mà không làm thay đổi giá trị.

### 3.4. Phần tử trung hòa

Một phần tử trung hòa là một giá trị mà khi thực hiện phép toán với nó, giá trị ban đầu không thay đổi.

Đối với phép cộng, số $0$ là phần tử trung hòa:

$$
\boxed{a+0=0+a=a}.
$$

Đối với phép nhân, số $1$ là phần tử trung hòa:

$$
\boxed{a\times1=1\times a=a}.
$$

Hai phần tử này có vai trò khác nhau:

- Số $0$ là phần tử trung hòa của phép cộng.
- Số $1$ là phần tử trung hòa của phép nhân.

### 3.5. Số đối và phép trừ

Với một số nguyên $a$, số $-a$ được gọi là số đối của $a$.

Hai số đối nhau khi cộng lại sẽ cho kết quả bằng $0$:

$$
\boxed{a+(-a)=0}.
$$

Từ khái niệm số đối, chúng ta có thể biểu diễn phép trừ dưới dạng phép cộng:

$$
\boxed{a-b=a+(-b)}.
$$

Ví dụ:

$$
7-10=7+(-10)=-3.
$$

### 3.6. Tính chất của số $0$ trong phép nhân

Số $0$ còn có một tính chất quan trọng:

$$
\boxed{a\times0=0}.
$$

Cần phân biệt tính chất này với tính chất phần tử trung hòa.

Số $0$ không phải phần tử trung hòa của phép nhân, vì tích của một số với $0$ luôn bằng $0$, chứ không phải luôn bằng số ban đầu.

### 3.7. Tập hợp số nguyên có đóng đối với những phép toán nào?

Một tập hợp được gọi là đóng đối với một phép toán nếu thực hiện phép toán đó trên các phần tử của tập hợp luôn cho kết quả vẫn thuộc tập hợp.

Đối với tập hợp số nguyên:

- Tổng của hai số nguyên luôn là số nguyên.
- Hiệu của hai số nguyên luôn là số nguyên.
- Tích của hai số nguyên luôn là số nguyên.

Tuy nhiên, phép chia hai số nguyên không phải lúc nào cũng cho kết quả nguyên.

Vì vậy, tập hợp số nguyên đóng đối với phép cộng, trừ và nhân, nhưng không đóng đối với phép chia.

---

## 4. Phép chia trong tập hợp số nguyên

### 4.1. Tại sao phép chia cần được xem xét riêng?

Xét hai phép chia:

$$
6\div3=2
$$

và:

$$
5\div3=\frac53.
$$

Kết quả của phép chia thứ nhất là một số nguyên, trong khi kết quả thứ hai không thuộc tập hợp số nguyên.

Điều này có nghĩa là phép chia hai số nguyên không phải lúc nào cũng tạo ra một số nguyên.

Cần phân biệt:

- Phép chia vẫn có thể thực hiện được trong tập hợp số hữu tỉ.
- Kết quả của phép chia không nhất thiết thuộc tập hợp số nguyên.

Ngoài ra, phép chia cho $0$ không được xác định.

### 4.2. Thương nguyên và số dư

Khi thực hiện phép chia một số nguyên cho một số nguyên dương, thay vì chỉ quan tâm đến kết quả dưới dạng phân số, chúng ta có thể biểu diễn phép chia bằng hai giá trị:

- Thương nguyên.
- Số dư.

Ví dụ, chia $17$ cho $3$:

$$
17=3\times5+2.
$$

Trong đó:

- $17$ là số bị chia.
- $3$ là số chia.
- $5$ là thương nguyên.
- $2$ là số dư.

Tương tự:

$$
20=6\times3+2.
$$

Ở đây, thương nguyên là $3$, còn số dư là $2$.

### 4.3. Định lý chia có dư

Với một số nguyên $a$ và một số nguyên dương $b$, luôn tồn tại duy nhất hai số nguyên $q,r$ sao cho:

$$
\boxed{a=bq+r}
$$

với điều kiện:

$$
\boxed{0\le r<b}.
$$

Đây được gọi là định lý chia có dư.

Trong đó:

- $a$ là số bị chia.
- $b$ là số chia và phải lớn hơn $0$.
- $q$ là thương nguyên.
- $r$ là số dư.

Định lý này vẫn đúng khi $a$ là số âm.

Ví dụ:

$$
-17=5\times(-4)+3.
$$

Ở đây:

$$
q=-4,\qquad r=3.
$$

Vì:

$$
0\le3<5,
$$

nên thương nguyên là $-4$ và số dư là $3$.

### 4.4. Tại sao số dư phải nằm từ $0$ đến $b-1$?

Theo định lý chia có dư:

$$
a=bq+r
$$

với:

$$
0\le r<b.
$$

Nếu số dư vẫn lớn hơn hoặc bằng số chia, chúng ta có thể tiếp tục lấy thêm một nhóm có kích thước bằng số chia, đồng thời tăng thương và giảm số dư.

Ví dụ:

$$
8=3\times1+5.
$$

Ta có thể viết lại:

$$
8=3\times2+2.
$$

Cách biểu diễn thứ hai có số dư nhỏ hơn và thỏa mãn điều kiện của định lý chia có dư.

Do $r$ là số nguyên, các giá trị có thể có của nó chỉ là:

$$
0,1,2,\ldots,b-1.
$$

Ví dụ, khi chia cho $5$, số dư chỉ có thể là:

$$
0,1,2,3,4.
$$

### 4.5. Tính duy nhất của thương nguyên và số dư

Định lý chia có dư không chỉ khẳng định thương nguyên và số dư tồn tại, mà còn khẳng định chúng là duy nhất.

Điều này có nghĩa là với một cặp số $a,b$ đã cho, trong điều kiện:

$$
a=bq+r,\qquad0\le r<b,
$$

không thể có hai cặp thương và số dư khác nhau cùng thỏa mãn.

Ví dụ:

$$
17=3\times5+2
$$

là biểu diễn hợp lệ.

Mặc dù:

$$
17=3\times4+5
$$

cũng là một đẳng thức đúng về mặt đại số, nhưng số dư $5$ không nhỏ hơn số chia $3$.

Vì vậy, cách biểu diễn thứ hai không thỏa mãn định lý chia có dư.

Tính duy nhất đảm bảo rằng mỗi phép chia có dư đều cho một kết quả xác định.

---

## 5. Phép toán modulo — Tìm số dư

### 5.1. Modulo là gì?

Trong toán học, đôi khi chúng ta không cần quan tâm đến toàn bộ kết quả của một phép chia. Thay vào đó, chúng ta chỉ quan tâm đến phần còn lại.

Phép toán dùng để lấy phần còn lại đó được gọi là phép toán modulo.

Ký hiệu:

$$
a\bmod b.
$$

Trong bài học này, chúng ta luôn giả sử:

$$
a\in\mathbb Z,\qquad b\in\mathbb Z,\qquad b>0.
$$

Giá trị của phép modulo chính là số dư trong định lý chia có dư.

Ví dụ:

$$
17\bmod3=2
$$

vì:

$$
17=3\times5+2.
$$

Tương tự:

$$
14\bmod5=4.
$$

### 5.2. Tại sao phép modulo hữu ích?

Phép modulo giúp chúng ta tập trung vào phần dư thay vì toàn bộ giá trị của một phép chia.

Ví dụ, khi xét thời gian trên đồng hồ 12 giờ, sau 15 giờ kể từ thời điểm 10 giờ, chúng ta có:

$$
10+15=25.
$$

Tuy nhiên, đồng hồ chỉ có 12 vị trí giờ.

Chúng ta có thể sử dụng modulo:

$$
25\bmod12=1.
$$

Vậy thời điểm tương ứng là 1 giờ.

Một ví dụ khác là những sự kiện lặp lại theo chu kỳ. Nếu một chu kỳ kéo dài $7$ ngày, chúng ta có thể sử dụng số dư khi chia cho $7$ để xác định vị trí của một thời điểm trong chu kỳ.

Phép modulo đặc biệt hữu ích khi làm việc với những hệ thống có tính chu kỳ.

### 5.3. Giới hạn của kết quả modulo

Từ định lý chia có dư, với số chia $b>0$, chúng ta luôn có:

$$
a=bq+r
$$

và:

$$
0\le r<b.
$$

Vì kết quả modulo chính là $r$, nên:

$$
\boxed{0\le a\bmod b<b}.
$$

Ví dụ, khi tính một số nguyên bất kỳ modulo $5$, kết quả chỉ có thể là:

$$
0,1,2,3,4.
$$

Không thể có kết quả bằng $5$, lớn hơn $5$ hoặc nhỏ hơn $0$.

---

## 6. Modulo với số âm

### 6.1. Một câu hỏi quan trọng

Chúng ta đã biết:

$$
5\bmod3=2.
$$

Vậy điều gì xảy ra nếu số bị chia là số âm?

Chẳng hạn:

$$
-1\bmod3=?
$$

Để giải quyết, chúng ta quay lại định nghĩa của phép chia có dư.

Với số nguyên $a$ và số nguyên dương $b$, cần tìm $q,r$ sao cho:

$$
a=bq+r
$$

và:

$$
0\le r<b.
$$

Ngay cả khi $a$ âm, số dư $r$ vẫn phải không âm.

### 6.2. Ví dụ thứ nhất: $-1\bmod3$

Chúng ta cần tìm $q,r$ sao cho:

$$
-1=3q+r
$$

với:

$$
0\le r<3.
$$

Chọn:

$$
q=-1.
$$

Khi đó:

$$
-1=3\times(-1)+2.
$$

Vì:

$$
0\le2<3,
$$

nên:

$$
\boxed{-1\bmod3=2}.
$$

Nếu chọn $q=0$, chúng ta sẽ nhận được số dư $-1$, không thỏa mãn điều kiện của định lý chia có dư.

### 6.3. Ví dụ thứ hai: $-5\bmod3$

Chúng ta cần tìm:

$$
-5=3q+r
$$

với:

$$
0\le r<3.
$$

Chọn:

$$
q=-2.
$$

Ta được:

$$
-5=3\times(-2)+1.
$$

Do đó:

$$
\boxed{-5\bmod3=1}.
$$

### 6.4. Công thức tính modulo của số âm

Giả sử:

$$
a<0,\qquad b>0.
$$

Đặt:

$$
s=|a|\bmod b.
$$

Có hai trường hợp.

**Trường hợp thứ nhất:**

Nếu:

$$
s=0,
$$

thì:

$$
a\bmod b=0.
$$

Ví dụ:

$$
-12\bmod4=0.
$$

**Trường hợp thứ hai:**

Nếu:

$$
s\ne0,
$$

thì:

$$
a\bmod b=b-s.
$$

Ví dụ:

$$
|-5|\bmod3=2.
$$

Do đó:

$$
-5\bmod3=3-2=1.
$$

Vậy công thức tổng quát là:

$$
\boxed{
a\bmod b=
\begin{cases}
0,&|a|\bmod b=0,\\
b-(|a|\bmod b),&|a|\bmod b\ne0.
\end{cases}
}
$$

### 6.5. Tại sao cần xét riêng trường hợp số dư bằng $0$?

Nếu chúng ta sử dụng công thức:

$$
a\bmod b=b-(|a|\bmod b)
$$

trong mọi trường hợp, đôi khi kết quả sẽ sai.

Ví dụ:

$$
-12\bmod4.
$$

Nếu áp dụng công thức mà không xét điều kiện, chúng ta nhận được:

$$
4-(12\bmod4)=4.
$$

Nhưng kết quả đúng phải là $0$.

Nguyên nhân là vì số dư luôn phải nhỏ hơn số chia.

Do đó, chúng ta phải tách riêng trường hợp số dư ban đầu bằng $0$.

### 6.6. Một số ví dụ tổng hợp

| Phép toán | Kết quả | Biểu diễn |
|---|---:|---|
| $-1\bmod3$ | $2$ | $-1=3(-1)+2$ |
| $-5\bmod3$ | $1$ | $-5=3(-2)+1$ |
| $-8\bmod3$ | $1$ | $-8=3(-3)+1$ |
| $-12\bmod4$ | $0$ | $-12=4(-3)+0$ |
| $-17\bmod5$ | $3$ | $-17=5(-4)+3$ |

Qua những ví dụ trên, chúng ta có thể thấy rằng số bị chia âm không đồng nghĩa với số dư âm.

Theo định nghĩa đang sử dụng, số dư luôn nằm trong khoảng:

$$
0\le r<b.
$$

---

## 7. Mở rộng: Tính chẵn và tính lẻ

Sau khi hiểu phép modulo, chúng ta có thể sử dụng nó để mô tả một tính chất quan trọng của số nguyên: tính chẵn và tính lẻ.

### 7.1. Số chẵn là gì?

Một số nguyên được gọi là số chẵn nếu nó có thể biểu diễn dưới dạng:

$$
\boxed{n=2k}
$$

trong đó:

$$
k\in\mathbb Z.
$$

Ví dụ:

$$
8=2\times4
$$

và:

$$
-6=2\times(-3).
$$

Do đó, cả $8$ và $-6$ đều là số chẵn.

Số $0$ cũng là số chẵn vì:

$$
0=2\times0.
$$

### 7.2. Số lẻ là gì?

Một số nguyên được gọi là số lẻ nếu nó có thể biểu diễn dưới dạng:

$$
\boxed{n=2k+1}
$$

trong đó:

$$
k\in\mathbb Z.
$$

Ví dụ:

$$
7=2\times3+1
$$

và:

$$
-3=2\times(-2)+1.
$$

Do đó, $7$ và $-3$ đều là số lẻ.

### 7.3. Mối liên hệ giữa tính chẵn lẻ và modulo

Khi chia một số nguyên cho $2$, số dư chỉ có thể là:

$$
0\quad\text{hoặc}\quad1.
$$

Vì vậy:

$$
\boxed{
n\bmod2=
\begin{cases}
0,&n\text{ là số chẵn},\\
1,&n\text{ là số lẻ}.
\end{cases}
}
$$

Ví dụ:

$$
14\bmod2=0
$$

nên $14$ là số chẵn.

Ngược lại:

$$
17\bmod2=1
$$

nên $17$ là số lẻ.

Tương tự:

$$
-8\bmod2=0
$$

và:

$$
-5\bmod2=1.
$$

### 7.4. Tại sao mọi số nguyên đều chẵn hoặc lẻ?

Với mọi số nguyên $n$, theo định lý chia có dư, tồn tại hai số nguyên $q,r$ sao cho:

$$
n=2q+r
$$

với:

$$
0\le r<2.
$$

Vì $r$ là số nguyên nên chỉ có hai khả năng:

$$
r=0\qquad\text{hoặc}\qquad r=1.
$$

Nếu $r=0$, ta có:

$$
n=2q.
$$

Theo định nghĩa, $n$ là số chẵn.

Nếu $r=1$, ta có:

$$
n=2q+1.
$$

Theo định nghĩa, $n$ là số lẻ.

Như vậy, mọi số nguyên đều là số chẵn hoặc số lẻ, và một số nguyên không thể đồng thời thuộc cả hai trường hợp.

---

# Bài tập về nhà

Các bài tập được sắp xếp theo mức độ tăng dần. Mỗi bài hướng đến một năng lực toán học cụ thể, từ vận dụng định nghĩa và suy luận ngược đến chứng minh tính chất và khai thác chu kỳ của phép toán modulo.

Đây không phải là những bài tập chỉ yêu cầu thay số vào công thức. Người học cần trình bày lập luận, giải thích các bước biến đổi và kiểm tra tính hợp lệ của kết quả.

## Bài 1. Phép chia có dư với số nguyên âm

Cho các cặp số nguyên $(a,b)$ sau:

$$
(-137,8),\qquad(-2026,17),\qquad(143,12),\qquad(-144,12).
$$

Với mỗi cặp, hãy tìm hai số nguyên $q,r$ sao cho:

$$
a=bq+r
$$

và:

$$
0\le r<b.
$$

Yêu cầu:

a. Tìm thương nguyên $q$ và số dư $r$ của từng trường hợp.

b. Kiểm tra lại mỗi kết quả bằng cách thay vào đẳng thức ban đầu.

c. Giải thích tại sao không thể sử dụng trực tiếp kết quả của phép chia thông thường rồi bỏ phần thập phân để xác định thương nguyên khi số bị chia âm.

d. Phân tích vai trò của điều kiện $0\le r<b$ trong việc xác định duy nhất thương nguyên và số dư.

## Bài 2. Bài toán ngược về số dư

Cho một số nguyên $n$ thỏa mãn:

$$
-80\le n\le80
$$

và:

$$
n\bmod11=7.
$$

a. Hãy tìm tất cả các giá trị nguyên có thể có của $n$.

b. Có bao nhiêu giá trị thỏa mãn điều kiện trên?

c. Tính tổng tất cả các giá trị tìm được mà không cần thực hiện phép cộng từng số một.

d. Giải thích tại sao hai số nguyên liên tiếp trong dãy nghiệm phải có hiệu bằng $11$.

e. Tổng quát hóa: Với modulo $m>0$, hãy mô tả cách tìm tất cả số nguyên $n$ nằm trong một đoạn $[L,U]$ và có số dư bằng $r$.

## Bài 3. Các tính chất của phép toán modulo

Cho $a,b$ là hai số nguyên bất kỳ và $m$ là một số nguyên dương.

Giả sử:

$$
a=mq+r
$$

và:

$$
b=ms+t
$$

trong đó:

$$
0\le r,t<m.
$$

a. Chứng minh rằng số dư của $a+b$ khi chia cho $m$ chính là:

$$
(r+t)\bmod m.
$$

b. Chứng minh rằng số dư của $ab$ khi chia cho $m$ chính là:

$$
(rt)\bmod m.
$$

c. Sử dụng hai kết quả trên để tính:

$$
(2026\times2027+2028^2)\bmod11.
$$

d. Giải thích tại sao khi tính modulo của một biểu thức lớn, chúng ta có thể thay các số ban đầu bằng số dư tương ứng để giảm độ phức tạp của phép tính.

Không được tính trực tiếp các tích lớn ở câu c. Hãy sử dụng các tính chất vừa chứng minh.

## Bài 4. Xây dựng công thức modulo cho số âm

Cho $a$ là một số nguyên âm và $m$ là một số nguyên dương.

Đặt:

$$
r=|a|\bmod m.
$$

a. Dựa trên định lý chia có dư, hãy chứng minh rằng:

$$
a\bmod m=
\begin{cases}
0,&r=0,\\
m-r,&r\ne0.
\end{cases}
$$

b. Giải thích tại sao phải tách riêng trường hợp $r=0$.

c. Sử dụng kết quả trên để tính:

$$
-2026\bmod17,
$$

$$
-314159\bmod100,
$$

$$
-999999\bmod37.
$$

d. Tìm một công thức biểu diễn số dư của $-a$ theo số dư của $a$, với $a$ là số nguyên bất kỳ và modulo $m>0$.

e. Xác định điều kiện để số dư của $a$ và $-a$ bằng nhau.

## Bài 5. Chứng minh các tính chất chẵn lẻ

Cho $n$ là một số nguyên bất kỳ.

a. Chứng minh rằng:

$$
n^2+n
$$

luôn là số chẵn.

b. Chứng minh rằng $n^2$ và $n$ luôn có cùng tính chẵn lẻ.

c. Xác định tính chẵn lẻ của biểu thức:

$$
P(n)=n^2+3n+1.
$$

Chứng minh kết quả đúng với mọi số nguyên $n$.

d. Xét biểu thức:

$$
Q(n)=n^2+2n+3.
$$

Hãy xác định tính chẵn lẻ của $Q(n)$ trong hai trường hợp $n$ chẵn và $n$ lẻ.

e. Trong các kết quả trên, hãy chỉ ra kết quả nào có thể được chứng minh trực tiếp bằng modulo $2$, sau đó trình bày một chứng minh sử dụng định nghĩa số chẵn và số lẻ.

## Bài 6. Khai thác chu kỳ của phép lũy thừa modulo

Cho hai biểu thức:

$$
A=3^{2025}
$$

và:

$$
B=7^{2026}.
$$

a. Tính các số dư của:

$$
3^1,3^2,3^3,3^4,3^5
$$

khi chia cho $100$.

b. Tìm một số nguyên dương $k$ sao cho:

$$
3^k\bmod100=1.
$$

c. Tương tự, hãy tìm một số nguyên dương $t$ sao cho:

$$
7^t\bmod100=1.
$$

d. Sử dụng các kết quả trên để tính:

$$
3^{2025}\bmod100
$$

và:

$$
7^{2026}\bmod100.
$$

e. Từ đó, hãy tính:

$$
\boxed{(3^{2025}+7^{2026})\bmod100}.
$$

f. Giải thích vì sao những chu kỳ xuất hiện trong phép tính có thể giúp chúng ta xử lý các số mũ rất lớn mà không cần tính giá trị đầy đủ của lũy thừa.

Không sử dụng các định lý số học nâng cao. Hãy xây dựng lập luận từ những kết quả modulo trực tiếp.

## Bài 7. Bài toán tổng hợp — Chu kỳ của nhiều lũy thừa

Xét biểu thức phụ thuộc vào số nguyên dương $n$:

$$
S(n)=1^n+2^n+3^n+\cdots+9^n.
$$

a. Tính số dư của từng lũy thừa:

$$
1^n,2^n,\ldots,9^n
$$

khi chia cho $10$, với $n=2026$.

b. Tính:

$$
S(2026)\bmod10.
$$

c. Không sử dụng giá trị cụ thể $n=2026$, hãy tìm chu kỳ của từng dãy số dư:

$$
2^n\bmod10,\quad
3^n\bmod10,\quad
4^n\bmod10,\quad
7^n\bmod10,\quad
8^n\bmod10,\quad
9^n\bmod10.
$$

d. Từ những chu kỳ trên, chứng minh rằng:

$$
S(n)\bmod10=5
$$

với mọi số nguyên dương $n$ có dạng:

$$
n=4k+2,\qquad k\ge0.
$$

e. Giải thích vì sao không cần tính giá trị thực tế của bất kỳ lũy thừa lớn nào để chứng minh kết quả ở câu d.