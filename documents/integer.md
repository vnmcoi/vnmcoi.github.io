# Tuần 1 — Số nguyên và phép toán modulo

## 1. Các thế giới toán học

### 1.1. Toán học được xây dựng như thế nào?

Trong quá trình học toán, chúng ta thường gặp nhiều lĩnh vực khác nhau. Ở bậc phổ thông, một số lĩnh vực quen thuộc là đại số, hình học Euclid và lượng giác.

Mỗi lĩnh vực có những đối tượng, quy tắc và cách giải quyết vấn đề riêng. Chẳng hạn, hình học nghiên cứu các đối tượng như điểm, đường thẳng và tam giác; trong khi đại số thường làm việc với số, biến và các phép toán.

Vậy làm thế nào để chúng ta có thể xây dựng một lĩnh vực toán học mới?

Hãy tưởng tượng toán học giống như một bức tường được xây từ những viên gạch. Những viên gạch ở dưới cùng đại diện cho các định nghĩa và tính chất cơ bản. Từ đó, chúng ta sử dụng những điều đã biết để xây dựng các kết quả phức tạp hơn.

Trong toán học, quá trình này thường diễn ra theo ba bước:

1. Định nghĩa: Xác định chính xác đối tượng mà chúng ta muốn nghiên cứu.
2. Tính chất: Xác định những quy tắc đúng với các đối tượng đó.
3. Chứng minh: Giải thích tại sao một kết luận nhất định phải đúng dựa trên những điều đã biết.

Ví dụ, thay vì chỉ nói rằng tổng của hai số chẵn luôn là số chẵn, chúng ta có thể dùng định nghĩa của số chẵn để giải thích tại sao điều đó đúng.

Điều quan trọng là toán học không chỉ yêu cầu chúng ta biết một kết quả, mà còn khuyến khích chúng ta hiểu kết quả đó có nghĩa gì, tại sao nó đúng và chúng ta có thể sử dụng nó như thế nào.

Hình ảnh bức tường chỉ là một cách để hình dung quá trình xây dựng kiến thức. Trên thực tế, các ngành toán học có thể sử dụng những nền tảng và hệ tiên đề khác nhau, chứ không phải mọi kiến thức đều được xây dựng từ một danh sách tính chất đơn giản duy nhất.

Tự tìm hiểu thêm: [The 360-Page Proof That 1+1=2](https://youtu.be/ysNyWFQstto?si=1KZETTTqQFAePlFs).

### 1.2. Tại sao chúng ta học số nguyên?

Trong bài học này, chúng ta sẽ tập trung vào một lĩnh vực quan trọng của toán học: lý thuyết số, đặc biệt là việc nghiên cứu các số nguyên và những tính chất của chúng.

Lý thuyết số nghiên cứu các câu hỏi như:

- Số nào chia hết cho số nào?
- Làm thế nào để tìm ước chung lớn nhất của hai số?
- Vì sao tổng của hai số lẻ luôn là số chẵn?
- Làm thế nào để xác định số dư của một số sau khi chia?
- Tại sao một số có tính chất đặc biệt khi xét các chữ số của nó?

Một thuật toán nổi tiếng trong lĩnh vực này là thuật toán Euclid, được sử dụng để tìm ước chung lớn nhất của hai số nguyên.

Để hiểu được những ý tưởng như vậy, trước hết chúng ta cần làm quen với số nguyên và một số tính chất cơ bản của chúng.

## 2. Số nguyên — Một tập hợp số quen thuộc

### 2.1. Số nguyên là gì?

Trước tiên, hãy nhìn vào các số mà chúng ta đã biết:

$$ 0,\ 1,\ 2,\ 3,\ 4,\ 5,\ldots $$

Đây là các số tự nhiên theo một quy ước thường dùng. Ký hiệu tập hợp số tự nhiên là $\mathbb N$. Lưu ý rằng một số tài liệu không đưa $0$ vào $\mathbb N$, vì vậy chúng ta cần kiểm tra quy ước của từng tài liệu.

Tuy nhiên, trong thực tế, chúng ta còn gặp các số âm như $-1,-2,-3$. Nếu bổ sung những số âm này vào tập hợp số tự nhiên, đồng thời giữ lại số $0$, chúng ta nhận được tập hợp số nguyên:

$$ \mathbb Z=\ldots,-3,-2,-1,0,1,2,3,\ldots $$

Tại sao cần có số âm?

Hãy xét một số ví dụ:

- Nhiệt độ có thể thấp hơn $0^\circ\mathrm C$.
- Tài khoản có thể có số dư âm.
- Khi di chuyển trên một trục số, chúng ta có thể đi theo cả hai hướng.

Các số tự nhiên không đủ để biểu diễn tất cả những tình huống này. Số nguyên cung cấp một tập hợp số rộng hơn để chúng ta mô tả chúng.

### 2.2. Các tập hợp số liên hệ với nhau như thế nào?

Trong bài học này, chúng ta cần phân biệt ba tập hợp:

- $\mathbb N$: tập hợp số tự nhiên.
- $\mathbb Z$: tập hợp số nguyên.
- $\mathbb Q$: tập hợp số hữu tỉ.

Số hữu tỉ là những số có thể biểu diễn dưới dạng:

$$ \frac{p}{q},\qquad p,q\in\mathbb Z,\ q\ne0 $$

Ví dụ, $\frac12$, $-\frac34$ và $5=\frac51$ đều là số hữu tỉ.

Mối quan hệ giữa các tập hợp có thể hình dung như sau:

$$ \mathbb N\subseteq\mathbb Z\subseteq\mathbb Q $$

Điều này có nghĩa là mọi số tự nhiên đều là số nguyên, và mọi số nguyên đều là số hữu tỉ.

Tuy nhiên, không phải mọi số hữu tỉ đều là số nguyên. Chẳng hạn, $\frac12\in\mathbb Q$ nhưng $\frac12\notin\mathbb Z$.

Trong bài học này, chúng ta tập trung vào $\mathbb Z$. Những phép toán sắp được giới thiệu sẽ được xây dựng cho các số nguyên, dù một số quy tắc cũng đúng với những tập hợp số rộng hơn.

## 3. Những tính chất cơ bản của phép toán

Trước khi học một phép toán mới, chúng ta cần hiểu các quy tắc cơ bản mà mình đã biết.

Giả sử $a,b,c$ là các số nguyên.

### 3.1. Tính chất giao hoán

Tính chất giao hoán cho biết rằng khi đổi vị trí hai số trong phép cộng hoặc phép nhân, kết quả không thay đổi.

Đối với phép cộng:

$$ a+b=b+a $$

Ví dụ:

$$ 3+5=5+3=8 $$

Đối với phép nhân:

$$ a\times b=b\times a $$

Ví dụ:

$$ 3\times5=5\times3=15 $$

Tại sao tính chất này hữu ích?

Vì chúng ta có thể thay đổi thứ tự các số để tính toán thuận tiện hơn mà không làm thay đổi kết quả.

### 3.2. Tính chất kết hợp

Tính chất kết hợp cho biết rằng khi cộng hoặc nhân ba số, cách nhóm các số không làm thay đổi kết quả.

Đối với phép cộng:

$$ (a+b)+c=a+(b+c) $$

Đối với phép nhân:

$$ (a\times b)\times c=a\times(b\times c) $$

Ví dụ:

$$ (2+3)+4=2+(3+4)=9 $$

Tính chất này khác với tính chất giao hoán. Giao hoán nói về việc đổi vị trí các số, trong khi kết hợp nói về việc thay đổi cách nhóm các số.

### 3.3. Tính chất phân phối

Tính chất phân phối liên kết phép nhân với phép cộng:

$$ a(b+c)=ab+ac $$

Ví dụ:

$$ 3(4+2)=3\times4+3\times2 $$

Hai vế đều bằng $18$.

Tại sao điều này hữu ích?

Khi một biểu thức có nhiều phép toán, chúng ta có thể biến đổi biểu thức thành một dạng dễ tính hơn mà vẫn giữ nguyên giá trị.

### 3.4. Phần tử trung hòa và tính chất của số $0$

Đây là một điểm cần phân biệt chính xác.

Đối với phép cộng, số $0$ là phần tử trung hòa, vì:

$$ a+0=0+a=a $$

Đối với phép nhân, số $1$ là phần tử trung hòa, vì:

$$ a\times1=1\times a=a $$

Vậy $a\times0=0$ có phải là tính chất trung hòa không?

Không. Đây là tính chất của số $0$ trong phép nhân: tích của một số với $0$ luôn bằng $0$.

Như vậy, chúng ta có ba kết quả cần ghi nhớ:

$$ a+0=a,\qquad a\times1=a,\qquad a\times0=0 $$

Những tính chất này có vẻ quen thuộc vì chúng ta đã sử dụng chúng từ lâu. Tuy nhiên, khi học toán một cách có hệ thống, chúng ta cần biết chính xác tên gọi và ý nghĩa của từng tính chất.

## 4. Phép chia trong tập hợp số nguyên

### 4.1. Tại sao cần chú ý đến phép chia?

Trong các phép cộng, trừ và nhân, nếu hai số đều là số nguyên thì kết quả cũng là số nguyên.

Ví dụ:

$$ 3+5=8 $$

$$ 3-5=-2 $$

$$ 3\times5=15 $$

Nhưng phép chia lại khác.

Xét:

$$ 6\div3=2 $$

Kết quả là một số nguyên.

Tuy nhiên:

$$ 5\div3=\frac53 $$

Kết quả không thuộc tập hợp số nguyên.

Điều này có nghĩa là phép chia hai số nguyên không phải lúc nào cũng tạo ra một số nguyên.

Đây là điểm quan trọng: chúng ta không thể nói rằng phép chia hoàn toàn không tồn tại trong số nguyên. Thay vào đó, chúng ta nói rằng tập hợp số nguyên không đóng đối với phép chia, bởi có những phép chia cho kết quả nằm ngoài tập hợp này.

### 4.2. Vậy làm thế nào để chia trong số nguyên?

Khi làm việc với số nguyên, chúng ta thường quan tâm đến hai giá trị:

- Thương nguyên: số lần mà số chia được lấy trọn trong quá trình chia.
- Số dư: phần còn lại sau khi lấy đi một số lần nguyên của số chia.

Ví dụ, khi chia $17$ cho $3$, chúng ta có:

$$ 17=3\times5+2 $$

Trong đó:

- $17$ là số bị chia.
- $3$ là số chia.
- $5$ là thương nguyên.
- $2$ là số dư.

Tại sao cần tách phép chia thành thương nguyên và số dư?

Vì ngay cả khi kết quả của phép chia thông thường không phải số nguyên, chúng ta vẫn có thể tìm được một thương nguyên và một số dư để mô tả mối quan hệ giữa hai số.

Ví dụ:

$$ 20=6\times3+2 $$

Ở đây, thương nguyên là $3$, còn số dư là $2$.

### 4.3. Quy tắc tổng quát

Với một số nguyên $a$ và một số nguyên dương $b$, chúng ta luôn có thể tìm được hai số nguyên $q,r$ sao cho:

$$ a=bq+r $$

với điều kiện:

$$ 0\le r<b $$

Trong biểu thức này:

- $a$ là số bị chia.
- $b$ là số chia và phải lớn hơn $0$.
- $q$ là thương nguyên.
- $r$ là số dư.

Điểm đặc biệt là quy tắc này vẫn đúng khi $a$ là số âm. Chúng ta sẽ xem xét trường hợp đó sau khi hiểu phép toán modulo.

## 5. Phép toán modulo — Tìm số dư

### 5.1. Modulo là gì?

Trong lập trình và lý thuyết số, chúng ta thường cần tìm số dư thay vì tìm toàn bộ kết quả của phép chia.

Phép toán dùng để lấy số dư được gọi là phép toán modulo, thường được viết bằng ký hiệu $\bmod$.

Ví dụ:

$$ 17\bmod3=2 $$

Tại sao kết quả bằng $2$?

Bởi vì khi chia $17$ cho $3$, chúng ta có:

$$ 17=3\times5+2 $$

Sau khi lấy đi $5$ nhóm, mỗi nhóm gồm $3$ đơn vị, còn lại $2$ đơn vị.

Vì vậy, số dư chính là $2$.

Tương tự:

$$ 5\bmod3=2 $$

vì:

$$ 5=3\times1+2 $$

Một cách viết tổng quát là:

$$ a\bmod b=r $$

khi:

$$ a=bq+r,\qquad 0\le r<b $$

Trong bài học này, chúng ta luôn giả sử $a\in\mathbb Z$ và $b$ là số nguyên dương.

### 5.2. Tại sao số dư chỉ có thể nằm từ $0$ đến $b-1$?

Đây là một câu hỏi quan trọng, vì nếu hiểu được điều này, chúng ta sẽ hiểu tại sao modulo hoạt động như vậy.

Giả sử chia một số nguyên cho $b=3$.

Nếu số dư bằng $3$, điều gì xảy ra?

Ví dụ:

$$ 8=3\times1+5 $$

Ta có thể viết:

$$ 8=3\times2+2 $$

Rõ ràng, cách biểu diễn thứ hai có số dư nhỏ hơn. Khi số dư vẫn lớn hơn hoặc bằng số chia, chúng ta có thể lấy thêm một nhóm nữa, làm tăng thương và giảm số dư.

Vì vậy, số dư phải nhỏ hơn số chia.

Mặt khác, số dư không thể âm theo quy ước đang sử dụng, vì khi đó chúng ta chưa chọn thương nguyên phù hợp để biểu diễn số bị chia.

Do đó:

$$ 0\le r<b $$

Vì $r$ là số nguyên, các giá trị có thể có của nó chỉ là:

$$ \boxed{0,1,2,\ldots,b-1} $$

Ví dụ, khi chia cho $5$, số dư chỉ có thể là $0,1,2,3$ hoặc $4$.

Không thể có số dư bằng $5$, vì khi đó chúng ta vẫn có thể lấy thêm một nhóm gồm $5$ đơn vị.

Hãy nhớ: Khi chia một số nguyên cho số nguyên dương $b$, số dư theo quy ước toán học luôn thuộc khoảng từ $0$ đến $b-1$.

### 5.3. Bài tập suy nghĩ

Hãy tự tính các giá trị sau:

$$ 17\bmod3=? $$

$$ 14\bmod5=? $$

$$ 20\bmod4=? $$

Sau đó, hãy tự giải thích tại sao từng kết quả không thể lớn hơn hoặc bằng số chia.

Ở thời điểm này, bạn chưa cần sử dụng bất kỳ thuật toán phức tạp nào. Chỉ cần tìm một thương nguyên phù hợp rồi xác định phần còn lại.

## 6. Modulo với số âm

### 6.1. Một câu hỏi thú vị

Chúng ta đã biết:

$$ 5\bmod3=2 $$

Vậy điều gì xảy ra nếu số bị chia là số âm?

Chẳng hạn:

$$ -1\bmod3=? $$

Câu hỏi này có vẻ kỳ lạ. Làm sao một số âm lại có số dư dương?

Để trả lời, chúng ta không nên dựa vào trực giác của phép chia thông thường. Thay vào đó, hãy quay lại định nghĩa.

Với số nguyên $a$ và số nguyên dương $b$, chúng ta cần tìm $q,r$ sao cho:

$$ a=bq+r,\qquad 0\le r<b $$

Nghĩa là, ngay cả khi $a$ âm, số dư $r$ vẫn phải không âm và nhỏ hơn $b$.

### 6.2. Ví dụ thứ nhất: $-1\bmod3$

Chúng ta cần tìm số nguyên $q$ và $r$ thỏa mãn:

$$ -1=3q+r,\qquad 0\le r<3 $$

Hãy thử $q=-1$:

$$ -1=3\times(-1)+2 $$

Đẳng thức này đúng vì:

$$ -3+2=-1 $$

Đồng thời, $2$ thỏa mãn điều kiện $0\le2<3$.

Vậy:

$$ \boxed{-1\bmod3=2} $$

Tại sao không chọn $q=0$?

Nếu chọn $q=0$, ta được:

$$ -1=3\times0+(-1) $$

Mặc dù đẳng thức vẫn đúng, số dư $-1$ không thỏa mãn điều kiện $0\le r<3$.

Vì vậy, cách biểu diễn đó không phù hợp với quy ước modulo mà chúng ta đang dùng.

### 6.3. Ví dụ thứ hai: $-5\bmod3$

Tương tự, chúng ta cần tìm $q,r$ sao cho:

$$ -5=3q+r,\qquad 0\le r<3 $$

Chọn $q=-2$:

$$ -5=3\times(-2)+1 $$

Vì số dư $1$ thỏa mãn điều kiện nên:

$$ \boxed{-5\bmod3=1} $$

Hãy chú ý rằng chúng ta không lấy $-5$ chia cho $3$, rồi bỏ qua phần thập phân theo cách chia thông thường. Thay vào đó, chúng ta tìm thương nguyên và số dư thỏa mãn đúng định nghĩa.

### 6.4. Có thể tính modulo của số âm bằng giá trị tuyệt đối không?

Có. Nhưng chúng ta cần chú ý đến một trường hợp đặc biệt.

Giả sử $a<0$, và đặt:

$$ s=|a|\bmod b $$

Nếu $s=0$, điều đó có nghĩa là $|a|$ chia hết cho $b$. Khi ấy, $a$ cũng chia hết cho $b$, nên số dư bằng $0$.

Ví dụ:

$$ -6\bmod3=0 $$

Nếu $s>0$, số dư của số âm được tính bằng $b-s$.

Ví dụ:

$$ |-5|\bmod3=5\bmod3=2 $$

Do đó:

$$ -5\bmod3=3-2=1 $$

Vì vậy, công thức đầy đủ cho $a<0$ và $b>0$ là:

$$ \boxed{ a\bmod b= \begin{cases} 0, & |a|\bmod b=0,\\\ b-(|a|\bmod b), & |a|\bmod b\ne0. \end{cases} } $$

Tại sao cần chia thành hai trường hợp?

Vì nếu áp dụng công thức $b-(|a|\bmod b)$ khi số dư bằng $0$, chúng ta sẽ nhận được $b$, nhưng số dư đúng phải là $0$.

Chẳng hạn, nếu áp dụng công thức thiếu điều kiện cho $-6\bmod3$, ta sẽ nhận được:

$$ 3-(6\bmod3)=3-0=3 $$

Kết quả này sai vì số dư không thể bằng số chia.

### 6.5. Một lưu ý khi lập trình

Trong toán học, với $b>0$, modulo được định nghĩa sao cho số dư nằm trong khoảng $0$ đến $b-1$.

Tuy nhiên, trong một số ngôn ngữ lập trình, toán tử `%` với số âm có thể cho kết quả khác quy ước này. Chẳng hạn, trong C++, `-1 % 3` cho kết quả `-1`, chứ không phải `2`.

Vì vậy, khi làm bài toán có số âm, hãy phân biệt rõ định nghĩa toán học của modulo với cách ngôn ngữ lập trình xử lý phép chia lấy dư.

## 7. Mở rộng: Tính chẵn và tính lẻ

Sau khi hiểu modulo, chúng ta có thể sử dụng nó để mô tả tính chẵn và tính lẻ của một số nguyên.

### 7.1. Số chẵn là gì?

Một số nguyên được gọi là số chẵn nếu nó chia hết cho $2$.

Nói cách khác, số dư của nó khi chia cho $2$ bằng $0$.

Ví dụ:

$$ 8\bmod2=0 $$

Vì vậy, $8$ là số chẵn.

Ta cũng có thể biểu diễn mọi số chẵn dưới dạng:

$$ n=2k,\qquad k\in\mathbb Z $$

Ví dụ:

$$ 8=2\times4 $$

$$ -6=2\times(-3) $$

Như vậy, số âm vẫn có thể là số chẵn.

### 7.2. Số lẻ là gì?

Một số nguyên được gọi là số lẻ nếu số dư của nó khi chia cho $2$ bằng $1$.

Ví dụ:

$$ 7\bmod2=1 $$

Do đó, $7$ là số lẻ.

Tổng quát hơn, một số nguyên lẻ có thể được biểu diễn dưới dạng:

$$ n=2k+1,\qquad k\in\mathbb Z $$

Ví dụ:

$$ 7=2\times3+1 $$

$$ -3=2\times(-2)+1 $$

Vì vậy, $-3$ là số lẻ.

### 7.3. Tại sao mọi số nguyên đều chẵn hoặc lẻ?

Theo tính chất của modulo, khi chia một số nguyên cho $2$, số dư chỉ có thể là:

$$ 0\quad\text{hoặc}\quad1 $$

Nếu số dư là $0$, số đó là số chẵn.

Nếu số dư là $1$, số đó là số lẻ.

Không có trường hợp thứ ba. Vì vậy, mọi số nguyên đều là số chẵn hoặc số lẻ, và một số nguyên không thể vừa chẵn vừa lẻ.

Đây là một ví dụ cho thấy một quy tắc quen thuộc có thể được giải thích bằng cách sử dụng một định nghĩa toán học tổng quát hơn.

## 8. Tổng kết bài học

Trong tuần đầu tiên, chúng ta đã làm quen với các khái niệm sau:

- Số nguyên là những số thuộc tập hợp $\mathbb Z$, bao gồm số âm, số $0$ và số dương.
- Phép chia hai số nguyên không phải lúc nào cũng cho kết quả nguyên.
- Với $a\in\mathbb Z$ và $b\in\mathbb Z,\ b>0$, tồn tại duy nhất hai số nguyên $q,r$ sao cho $a=bq+r$ và $0\le r<b$.
- Phép toán modulo trả về số dư $r$.
- Khi số bị chia âm, số dư theo quy ước toán học vẫn không âm.
- Tính chẵn và tính lẻ có thể được xác định bằng modulo $2$.

Điều quan trọng nhất không phải là ghi nhớ thật nhiều công thức ngay lập tức. Thay vào đó, hãy hiểu mối liên hệ giữa chúng: định nghĩa của phép chia với số dư dẫn đến phép toán modulo, và modulo giúp chúng ta mô tả những tính chất như tính chẵn lẻ.

# Bài tập về nhà — 14 bài từ cơ bản đến nâng cao

Các bài tập dưới đây được sắp xếp theo mức độ tăng dần. Mục tiêu chủ yếu là củng cố định nghĩa, rèn khả năng tính toán và tập giải thích tại sao một kết quả đúng.

Đối với bài chứng minh, bạn không cần sử dụng quy nạp hay các kỹ thuật chứng minh phức tạp. Hãy trình bày bằng những bước rõ ràng, dựa trên định nghĩa đã học.

## Mức 1 — Nhớ định nghĩa và tính toán cơ bản

### Bài 1. Nhận biết số nguyên

Trong các số sau, số nào thuộc tập hợp số nguyên $\mathbb Z$?

$$ -7,\quad 0,\quad 3,\quad \frac12,\quad -2.5,\quad \frac63 $$

Với mỗi số, hãy giải thích ngắn gọn vì sao nó là hoặc không phải là số nguyên.

### Bài 2. Nhớ các tính chất cơ bản

Điền biểu thức thích hợp vào chỗ trống:

a. $a+b=\underline{\hspace{1cm}}$

b. $(a+b)+c=a+(\underline{\hspace{1cm}})$

c. $a(b+c)=\underline{\hspace{1cm}}$

d. $a+0=\underline{\hspace{1cm}}$

e. $a\times1=\underline{\hspace{1cm}}$

f. $a\times0=\underline{\hspace{1cm}}$

Sau đó, hãy cho biết biểu thức nào thể hiện tính chất giao hoán, kết hợp, phân phối, phần tử trung hòa hoặc tính chất của số $0$.

### Bài 3. Tìm thương nguyên và số dư

Tìm thương nguyên $q$ và số dư $r$ trong mỗi phép chia sau:

a. $17$ chia cho $5$.

b. $29$ chia cho $6$.

c. $36$ chia cho $9$.

d. $41$ chia cho $8$.

Với mỗi câu, hãy viết kết quả dưới dạng:

$$ a=bq+r $$

### Bài 4. Tính modulo

Tính các giá trị sau:

a. $13\bmod5$

b. $22\bmod7$

c. $36\bmod9$

d. $51\bmod10$

e. $100\bmod3$

Không chỉ ghi kết quả. Hãy viết một đẳng thức dạng $a=bq+r$ để giải thích ít nhất hai câu.

## Mức 2 — Hiểu số dư và xử lý số âm

### Bài 5. Số dư có thể nhận những giá trị nào?

Khi chia một số nguyên cho $b$, hãy liệt kê tất cả giá trị số dư có thể có trong các trường hợp sau:

a. $b=2$.

b. $b=4$.

c. $b=7$.

Sau đó, giải thích tại sao số dư không thể bằng $b$ hoặc lớn hơn $b$.

### Bài 6. Modulo với số âm

Tính các giá trị sau theo định nghĩa số dư không âm:

a. $-1\bmod3$.

b. $-5\bmod3$.

c. $-8\bmod3$.

d. $-12\bmod4$.

e. $-17\bmod5$.

Với mỗi câu, hãy tìm các số nguyên $q,r$ thỏa mãn:

$$ a=bq+r,\qquad 0\le r<b $$

### Bài 7. Tìm lỗi trong công thức

Một bạn viết công thức sau cho mọi số nguyên âm $a$ và số nguyên dương $b$:

$$ a\bmod b=b-(|a|\bmod b) $$

a. Hãy sử dụng công thức này để tính $-5\bmod3$.

b. Sử dụng cùng công thức để tính $-6\bmod3$.

c. Đối chiếu kết quả với định nghĩa modulo. Công thức trên sai ở trường hợp nào?

d. Hãy sửa công thức để nó đúng trong mọi trường hợp.

Gợi ý: Hãy xét riêng khi $|a|\bmod b=0$ và khi $|a|\bmod b\ne0$.

### Bài 8. Chẵn hay lẻ?

Xác định tính chẵn hoặc lẻ của các số sau:

$$ -11,\quad -8,\quad 0,\quad 17,\quad 24,\quad 101 $$

Sau đó, sử dụng modulo $2$ để giải thích kết quả.

## Mức 3 — Bắt đầu giải thích và chứng minh

### Bài 9. Chứng minh số dư nằm trong một khoảng

Theo định nghĩa, với số nguyên $a$ và số nguyên dương $b$, ta có:

$$ a=bq+r,\qquad 0\le r<b $$

Hãy giải thích bằng lời tại sao số dư chỉ có thể là một trong các số:

$$ 0,1,2,\ldots,b-1 $$

Bài này không yêu cầu một chứng minh hình thức. Chỉ cần giải thích rõ vì sao số dư phải không âm, nhỏ hơn $b$, và vì sao nó chỉ nhận các giá trị nguyên.

### Bài 10. Tại sao modulo $2$ chỉ có hai kết quả?

Hãy chứng minh rằng với mọi số nguyên $n$:

$$ n\bmod2\in0,1 $$

Sau đó, giải thích tại sao điều này có nghĩa là mọi số nguyên đều chẵn hoặc lẻ.

Bạn có thể sử dụng trực tiếp định nghĩa về thương nguyên và số dư. Không cần sử dụng quy nạp.

### Bài 11. Hai số cách nhau một bội của $b$

Hãy tính:

$$ 8\bmod5,\qquad 13\bmod5,\qquad 18\bmod5 $$

Bạn nhận thấy điều gì?

Tiếp theo, hãy giải thích tại sao $a$ và $a+kb$ có cùng số dư khi chia cho $b$, với $a,k\in\mathbb Z$ và $b$ là số nguyên dương.

Gợi ý: Giả sử:

$$ a=bq+r $$

Hãy viết lại $a+kb$ dưới dạng một bội của $b$ cộng với $r$.

## Mức 4 — Ứng dụng vào chữ số và bài toán đảo số

### Bài 12. Đảo ngược một số có hai chữ số

Cho một số nguyên dương có hai chữ số:

$$ n=10a+b $$

Trong đó $a$ là chữ số hàng chục và $b$ là chữ số hàng đơn vị.

Số thu được khi đảo ngược hai chữ số là:

$$ m=10b+a $$

Ví dụ, nếu $n=37$, thì $m=73$.

a. Hãy tính $n-m$ theo $a$ và $b$.

b. Chứng minh rằng hiệu $n-m$ luôn chia hết cho $9$.

c. Kiểm tra kết quả với các số $24$, $51$ và $86$.

Gợi ý: Hãy khai triển $n-m$, sau đó đặt nhân tử chung. Bạn chỉ cần dùng phép biến đổi đại số cơ bản.

### Bài 13. Chia hết cho $3$ và tổng các chữ số

Cho số nguyên dương có hai chữ số:

$$ n=10a+b $$

Trong đó $a$ là chữ số hàng chục và $b$ là chữ số hàng đơn vị.

a. Hãy viết $n$ dưới dạng tổng của $a+b$ và một bội của $3$.

b. Sử dụng modulo để giải thích tại sao:

$$ n\bmod3=(a+b)\bmod3 $$

c. Từ kết quả trên, hãy nêu quy tắc kiểm tra một số có hai chữ số có chia hết cho $3$ hay không dựa vào tổng các chữ số.

d. Áp dụng quy tắc cho các số $42$, $57$, $68$ và $93$.

### Bài 14. Đảo ngược một số có ba chữ số

Cho một số có ba chữ số:

$$ n=100a+10b+c $$

Trong đó $a$ là chữ số hàng trăm, $b$ là chữ số hàng chục và $c$ là chữ số hàng đơn vị.

Số thu được khi đảo ngược thứ tự các chữ số được biểu diễn bởi:

$$ m=100c+10b+a $$

a. Hãy tính $n-m$ theo $a,b,c$.

b. Chứng minh rằng $n-m$ luôn chia hết cho $99$.

c. Từ kết quả đó, hãy giải thích tại sao $n-m$ cũng luôn chia hết cho $9$ và $11$.

d. Kiểm tra kết quả với số $123$, số đảo ngược là $321$.

Gợi ý: Bạn không cần kiến thức toán học nâng cao. Chỉ cần viết hai biểu thức, trừ chúng cho nhau và đặt nhân tử chung. Hãy nhớ rằng $99=9\times11$.

## Cách học để nhớ bài lâu hơn

Không nhất thiết phải giải cả 14 bài trong một lần. Một cách học hữu ích là chia bài tập thành ba lượt:

Lượt 1 — Nhớ định nghĩa: Làm các bài 1–8. Mục tiêu là tính đúng và sử dụng đúng khái niệm.

Lượt 2 — Giải thích: Làm các bài 9–11. Mục tiêu là trình bày được tại sao một tính chất đúng, thay vì chỉ ghi nhớ kết quả.

Lượt 3 — Vận dụng: Làm các bài 12–14. Mục tiêu là nhận ra những tính chất modulo có thể được sử dụng để giải thích các bài toán về chữ số.

Một quy tắc nên duy trì trong suốt quá trình học là: khi đưa ra một kết luận, hãy cố gắng viết thêm một hoặc hai câu giải thích tại sao kết luận ấy đúng.