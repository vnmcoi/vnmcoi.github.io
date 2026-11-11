# Tuần 1 — Giới thiệu về Competitive Programming và C++

## 1. Competitive Programming — Thi đấu lập trình

### 1.1. Competitive Programming là gì?

Competitive Programming, thường được viết tắt là CP, là một hình thức giải quyết các bài toán bằng cách thiết kế thuật toán và hiện thực hóa chúng thông qua ngôn ngữ lập trình.

Trong CP, người tham gia nhận được một bài toán với những yêu cầu và điều kiện cụ thể. Nhiệm vụ là xây dựng một chương trình có thể giải quyết bài toán đó một cách chính xác và hiệu quả.

Các bài toán có thể liên quan đến:

- Toán học và lý thuyết số.
- Xử lý dữ liệu và chuỗi ký tự.
- Cấu trúc dữ liệu.
- Đồ thị và các bài toán trên đồ thị.
- Quy hoạch động.
- Tối ưu hóa.
- Hình học tính toán.

Điểm đặc biệt của Competitive Programming là người giải không chỉ cần tìm ra một phương pháp đúng, mà còn phải quan tâm đến khả năng thực thi của phương pháp đó.

Một lời giải có thể hoàn toàn đúng về mặt toán học nhưng vẫn không được chấp nhận nếu chương trình chạy quá lâu hoặc sử dụng quá nhiều bộ nhớ.

Vì vậy, trong CP, chúng ta thường phải quan tâm đến ba yếu tố:

**1. Tính đúng đắn (Correctness)**

Chương trình phải giải quyết chính xác yêu cầu của bài toán và cho ra kết quả đúng đối với mọi trường hợp nằm trong phạm vi đề bài.

**2. Hiệu quả (Efficiency)**

Chương trình phải sử dụng thời gian và bộ nhớ hợp lý để xử lý dữ liệu đầu vào.

**3. Tính hiện thực (Implementation)**

Một ý tưởng giải toán tốt cần được chuyển thành chương trình có cấu trúc rõ ràng, hoạt động chính xác và không mắc lỗi trong quá trình thực thi.

Ba yếu tố này có mối quan hệ chặt chẽ với nhau. Một lời giải tốt không chỉ cần đúng mà còn phải có khả năng chạy được trong những giới hạn mà bài toán đưa ra.

### 1.2. Competitive Programming khác gì với lập trình thông thường?

Lập trình là quá trình xây dựng chương trình máy tính để thực hiện một nhiệm vụ nhất định.

Chẳng hạn:

- Xây dựng một trang web.
- Phát triển một ứng dụng điện thoại.
- Quản lý cơ sở dữ liệu.
- Tạo một phần mềm chỉnh sửa hình ảnh.
- Xây dựng hệ thống xử lý dữ liệu.

Trong khi đó, Competitive Programming tập trung vào việc giải quyết các bài toán có cấu trúc rõ ràng, thường yêu cầu người tham gia tìm ra một thuật toán phù hợp.

Điều này không có nghĩa CP không phải là lập trình. Ngược lại, CP là một môi trường rèn luyện khả năng giải quyết vấn đề bằng lập trình.

Sự khác biệt chủ yếu nằm ở mục tiêu:

- Lập trình ứng dụng thường hướng đến việc xây dựng một sản phẩm hoặc hệ thống đáp ứng nhu cầu thực tế.
- Competitive Programming hướng đến việc tìm kiếm và hiện thực hóa những lời giải chính xác, hiệu quả cho các bài toán được đưa ra.

Hai lĩnh vực này có thể sử dụng chung nhiều kiến thức về thuật toán, cấu trúc dữ liệu và ngôn ngữ lập trình.

### 1.3. Tại sao cần học Competitive Programming?

Một trong những lý do quan trọng nhất là CP giúp chúng ta phát triển tư duy giải quyết vấn đề.

Khi gặp một bài toán mới, người giải cần:

1. Đọc và xác định chính xác yêu cầu.
2. Phân tích dữ liệu đầu vào và kết quả cần tìm.
3. Nhận ra những tính chất toán học hoặc cấu trúc có liên quan.
4. Xây dựng một phương pháp giải.
5. Đánh giá tính đúng đắn và hiệu quả của phương pháp.
6. Hiện thực hóa phương pháp bằng ngôn ngữ lập trình.

Quá trình này không chỉ giúp chúng ta học cách viết chương trình mà còn rèn luyện khả năng phân tích, trừu tượng hóa và xây dựng lập luận.

Một bài toán có thể có nhiều cách giải khác nhau. Tuy nhiên, không phải cách giải nào cũng phù hợp với giới hạn dữ liệu của bài toán.

Đây chính là lý do chúng ta cần nghiên cứu thuật toán.

---

## 2. Thuật toán — Nền tảng của việc giải quyết vấn đề

### 2.1. Thuật toán là gì?

Thuật toán (Algorithm) là một tập hợp hữu hạn các bước được xác định rõ ràng, có thứ tự và có thể thực hiện được nhằm giải quyết một bài toán hoặc một lớp bài toán nhất định.

Nói cách khác, thuật toán mô tả cách chúng ta đi từ dữ liệu đầu vào đến kết quả mong muốn.

Một thuật toán thường có ba thành phần cơ bản:

- **Đầu vào (Input):** Dữ liệu được cung cấp cho thuật toán.
- **Quá trình xử lý (Process):** Các bước thực hiện để giải quyết bài toán.
- **Đầu ra (Output):** Kết quả mà thuật toán tạo ra.

Ví dụ, xét bài toán tìm số lớn nhất trong một dãy số nguyên.

Cho dãy:

$$
A=[3,8,2,11,5].
$$

Chúng ta cần tìm phần tử lớn nhất của dãy.

Một cách giải là:

1. Giả sử phần tử đầu tiên là số lớn nhất hiện tại.
2. Xét lần lượt các phần tử còn lại.
3. Nếu phần tử đang xét lớn hơn giá trị lớn nhất hiện tại, cập nhật giá trị lớn nhất.
4. Sau khi xét hết dãy, trả về giá trị lớn nhất.

Kết quả:

$$
\boxed{11}
$$

Đây là một thuật toán vì chúng ta đã xác định được một chuỗi bước thực hiện cụ thể để giải quyết bài toán.

### 2.2. Một thuật toán không phải là một chương trình

Đây là một điểm cần phân biệt.

Thuật toán và chương trình máy tính có mối liên hệ chặt chẽ, nhưng chúng không phải cùng một khái niệm.

**Thuật toán** là phương pháp giải quyết bài toán, được mô tả bằng các bước logic.

**Chương trình** là cách chúng ta hiện thực hóa thuật toán bằng một ngôn ngữ lập trình để máy tính có thể thực thi.

Ví dụ, thuật toán tìm số lớn nhất trong một dãy có thể được mô tả bằng lời, bằng mã giả hoặc bằng lưu đồ.

Sau đó, chúng ta có thể hiện thực hóa thuật toán đó bằng:

- C++.
- Python.
- Java.
- Rust.

Mặc dù chương trình có thể được viết bằng những ngôn ngữ khác nhau, thuật toán về bản chất vẫn là một phương pháp giải quyết cùng một bài toán.

Điều này đặc biệt quan trọng trong Competitive Programming: chúng ta cần hiểu thuật toán trước khi quan tâm đến việc viết nó bằng ngôn ngữ nào.

### 2.3. Thuật toán không phải là một mẹo giải bài

Một lỗi thường gặp khi mới học CP là ghi nhớ một vài cách giải cho những bài toán cụ thể rồi cố gắng áp dụng chúng vào những bài toán khác.

Tuy nhiên, mục tiêu của việc học thuật toán không phải là ghi nhớ thật nhiều lời giải riêng lẻ.

Thay vào đó, chúng ta cần hiểu:

- Thuật toán giải quyết loại bài toán nào?
- Thuật toán dựa trên tính chất toán học nào?
- Những điều kiện nào phải được thỏa mãn?
- Trong trường hợp nào thuật toán không còn đúng?
- Có thể mở rộng hoặc kết hợp thuật toán với những phương pháp khác hay không?

Ví dụ, thuật toán Dijkstra được sử dụng để tìm đường đi ngắn nhất từ một đỉnh nguồn đến các đỉnh khác trong một đồ thị có trọng số không âm.

Ở đây, một số khái niệm cần được hiểu rõ:

**Đồ thị (Graph):** Một cấu trúc toán học bao gồm các đỉnh và các cạnh nối giữa chúng.

**Trọng số (Weight):** Một giá trị được gán cho cạnh, thường được sử dụng để biểu diễn chi phí hoặc độ dài khi di chuyển.

**Đỉnh (Vertex):** Một đối tượng trong đồ thị.

**Đường đi (Path):** Một dãy các đỉnh được kết nối thông qua những cạnh tương ứng.

**Đường đi ngắn nhất (Shortest Path):** Đường đi có tổng trọng số nhỏ nhất trong số những đường đi hợp lệ giữa hai đỉnh.

Thuật toán Dijkstra yêu cầu trọng số của các cạnh không âm. Nếu xuất hiện cạnh có trọng số âm, thuật toán không còn đảm bảo tính đúng đắn trong trường hợp tổng quát.

Vì vậy, không thể chỉ nhớ rằng Dijkstra là thuật toán tìm đường đi ngắn nhất rồi áp dụng nó cho mọi bài toán có liên quan đến đường đi.

Chúng ta phải hiểu rõ điều kiện và phạm vi sử dụng của thuật toán.

### 2.4. Tại sao cần đánh giá thuật toán?

Giả sử có hai thuật toán cùng giải quyết một bài toán và đều cho kết quả chính xác.

Thuật toán thứ nhất cần thực hiện một số lượng phép tính tăng theo bình phương kích thước dữ liệu đầu vào.

Thuật toán thứ hai chỉ cần thực hiện số lượng phép tính tăng tuyến tính theo kích thước dữ liệu đầu vào.

Khi dữ liệu nhỏ, sự khác biệt có thể chưa đáng kể.

Nhưng khi dữ liệu lớn, thuật toán thứ hai thường hiệu quả hơn rất nhiều.

Đây là lý do chúng ta cần một cách đánh giá thuật toán.

Trong Competitive Programming, hai khái niệm quan trọng được sử dụng là:

- **Độ phức tạp thời gian (Time Complexity):** Mô tả tốc độ tăng của lượng công việc tính toán khi kích thước đầu vào tăng.
- **Độ phức tạp bộ nhớ (Space Complexity):** Mô tả tốc độ tăng của lượng bộ nhớ cần sử dụng khi kích thước đầu vào tăng.

Những nội dung này sẽ được nghiên cứu sâu hơn trong các bài học về thuật toán.

Ở giai đoạn đầu, chúng ta chỉ cần hiểu rằng một lời giải không chỉ được đánh giá bằng tính đúng đắn mà còn bằng tài nguyên mà nó sử dụng.

---

## 3. Ngôn ngữ lập trình — Công cụ hiện thực hóa thuật toán

### 3.1. Ngôn ngữ lập trình là gì?

Máy tính không trực tiếp hiểu những mô tả thuật toán bằng ngôn ngữ tự nhiên như tiếng Việt hoặc tiếng Anh theo cách con người hiểu.

Để máy tính thực hiện một thuật toán, chúng ta cần biểu diễn các bước xử lý dưới dạng những câu lệnh mà hệ thống có thể dịch và thực thi.

Ngôn ngữ lập trình là hệ thống ký hiệu, cú pháp và quy tắc cho phép chúng ta viết những câu lệnh đó.

Một số ngôn ngữ lập trình thường gặp trong Competitive Programming là:

- C++.
- Python.
- Java.
- Rust.

Mỗi ngôn ngữ có những đặc điểm riêng về cú pháp, hiệu năng, hệ sinh thái thư viện và cách quản lý tài nguyên.

Tuy nhiên, một thuật toán không phụ thuộc hoàn toàn vào một ngôn ngữ lập trình cụ thể.

Chúng ta có thể xây dựng một phương pháp giải trước, sau đó lựa chọn ngôn ngữ phù hợp để hiện thực hóa nó.

### 3.2. Tại sao sử dụng C++?

C++ là một trong những ngôn ngữ được sử dụng rộng rãi trong Competitive Programming.

Có một số lý do quan trọng:

**Hiệu năng thực thi**

C++ là ngôn ngữ biên dịch, cho phép chương trình được chuyển thành mã máy trước khi thực thi.

Điều này thường mang lại hiệu năng tốt, đặc biệt trong những bài toán có lượng tính toán lớn.

**Khả năng kiểm soát tài nguyên**

C++ cung cấp nhiều cơ chế để quản lý bộ nhớ và các tài nguyên của chương trình.

Điều này hữu ích khi giải những bài toán có giới hạn bộ nhớ nghiêm ngặt.

**Thư viện chuẩn phong phú**

Thư viện chuẩn của C++ cung cấp nhiều cấu trúc dữ liệu và công cụ có sẵn, đặc biệt là Standard Template Library (STL).

Một số thành phần quan trọng bao gồm:

- `vector`: Mảng động.
- `string`: Chuỗi ký tự.
- `stack`: Ngăn xếp.
- `queue`: Hàng đợi.
- `set`: Tập hợp có thứ tự.
- `map`: Cấu trúc lưu trữ các cặp khóa và giá trị.
- `priority_queue`: Hàng đợi ưu tiên.
- `algorithm`: Thư viện chứa các thuật toán thông dụng.

Những công cụ này giúp chúng ta tập trung vào ý tưởng giải bài toán thay vì phải tự xây dựng lại mọi cấu trúc từ đầu.

### 3.3. Tại sao vẫn cần học Python?

Mặc dù C++ có lợi thế về hiệu năng trong nhiều bài toán, Python vẫn là một ngôn ngữ rất hữu ích trong Competitive Programming.

Python có một số đặc điểm đáng chú ý:

**Cú pháp ngắn gọn**

Python thường yêu cầu ít mã nguồn hơn để biểu diễn cùng một thao tác.

Điều này giúp việc thử nghiệm và hiện thực hóa ý tưởng trở nên thuận tiện.

**Xử lý số nguyên lớn**

Python hỗ trợ số nguyên có độ chính xác tùy ý trong phạm vi bộ nhớ khả dụng.

Vì vậy, chúng ta có thể thực hiện nhiều phép tính với những số nguyên rất lớn mà không cần tự xây dựng cơ chế quản lý tràn số như khi sử dụng các kiểu số nguyên có kích thước cố định trong C++.

**Các công cụ xử lý dữ liệu tiện lợi**

Python cung cấp nhiều chức năng có sẵn cho việc xử lý chuỗi, danh sách, từ điển và các phép toán trên dữ liệu.

Một số bài toán có thể được diễn đạt ngắn gọn hơn bằng Python.

Tuy nhiên, Python thường có tốc độ thực thi thấp hơn C++ trong nhiều tác vụ tính toán tương đương. Điều này có thể trở thành bất lợi khi bài toán có giới hạn thời gian nghiêm ngặt.

### 3.4. Tại sao nên học song song C++ và Python?

Trong chương trình này, chúng ta sẽ sử dụng cả C++ và Python.

Mỗi ngôn ngữ có vai trò riêng:

| Tiêu chí | C++ | Python |
|---|---|---|
| Hiệu năng | Thường cao | Thường thấp hơn C++ |
| Cú pháp | Chặt chẽ và chi tiết hơn | Ngắn gọn |
| Quản lý bộ nhớ | Có nhiều cơ chế kiểm soát trực tiếp | Tự động trong phần lớn trường hợp |
| Số nguyên lớn | Các kiểu số nguyên thông thường có giới hạn kích thước | Hỗ trợ số nguyên có độ chính xác tùy ý |
| Thư viện | STL rất hữu ích trong CP | Nhiều công cụ xử lý dữ liệu có sẵn |
| Ứng dụng trong chương trình | Ngôn ngữ chính của tài liệu | Ngôn ngữ bổ trợ và thực hành |

Việc học song song hai ngôn ngữ giúp chúng ta có thêm góc nhìn khi hiện thực hóa cùng một thuật toán.

Đặc biệt, khi đã hiểu một thuật toán, việc chuyển đổi nó giữa C++ và Python sẽ giúp chúng ta phân biệt rõ đâu là ý tưởng giải toán và đâu là cú pháp của ngôn ngữ lập trình.

### 3.5. Quy ước sử dụng ngôn ngữ trong tài liệu

Để thống nhất cách trình bày, chương trình này sử dụng những quy ước sau:

1. C++ là ngôn ngữ chính trong các ví dụ và phần hiện thực thuật toán.
2. Python được sử dụng song song để so sánh cách biểu diễn và mở rộng khả năng giải quyết vấn đề.
3. Những thuật toán và kiến thức toán học sẽ được giải thích độc lập với ngôn ngữ lập trình.
4. Khi một bài toán có sự khác biệt đáng chú ý về hiệu năng giữa hai ngôn ngữ, chúng ta sẽ phân tích riêng.

Điều quan trọng nhất là không nên nhầm lẫn giữa việc biết cú pháp của một ngôn ngữ với việc hiểu thuật toán.

Một người có thể viết được rất nhiều câu lệnh C++ nhưng vẫn chưa chắc có khả năng giải quyết những bài toán thuật toán phức tạp.

Ngược lại, khi đã nắm vững ý tưởng giải toán, việc học cách biểu diễn nó bằng một ngôn ngữ mới sẽ trở nên dễ dàng hơn.

---

## 4. C++ Fundamentals — Nền tảng C++

### 4.1. Tại sao cần học C++ Fundamentals?

Trước khi bắt đầu triển khai các thuật toán, chúng ta cần hiểu cách một chương trình C++ được viết và thực thi.

Một thuật toán có thể hoàn toàn đúng về mặt logic, nhưng nếu chúng ta không biết cách biểu diễn nó bằng cú pháp hợp lệ thì máy tính sẽ không thể thực hiện được.

C++ Fundamentals là phần kiến thức nền tảng giúp người học:

- Đọc và hiểu chương trình C++.
- Viết những chương trình cơ bản.
- Tiếp nhận dữ liệu từ đầu vào.
- Thực hiện các phép tính.
- Điều khiển luồng thực thi.
- Lưu trữ và xử lý dữ liệu.

Trong tuần đầu tiên, chúng ta sẽ tập trung vào những thành phần cần thiết nhất để bắt đầu giải các bài toán đơn giản.

### 4.2. Cấu trúc chương trình và nhập xuất dữ liệu

Một chương trình C++ cần có cấu trúc nhất định để trình biên dịch có thể hiểu và xử lý.

Ví dụ:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!";
    return 0;
}
```

Đây là một chương trình C++ cơ bản.

Những thành phần cần làm quen:

- `#include <iostream>`: Nạp thư viện hỗ trợ các thao tác nhập và xuất dữ liệu cơ bản.
- `using namespace std;`: Cho phép sử dụng trực tiếp các tên trong không gian tên `std` mà không cần viết tiền tố `std::`.
- `int main()`: Hàm chính, là điểm bắt đầu thực thi của chương trình.
- `cout`: Đưa dữ liệu ra đầu ra.
- `return 0`: Kết thúc hàm chính với giá trị trả về bằng \(0\), thường biểu thị chương trình kết thúc thành công.

Trong Competitive Programming, nhập và xuất dữ liệu là một trong những thao tác xuất hiện thường xuyên nhất.

Chúng ta cần biết cách đọc dữ liệu được cung cấp và đưa kết quả ra đúng định dạng mà đề bài yêu cầu.

### 4.3. Biến, kiểu dữ liệu và toán tử

Trong một chương trình, chúng ta thường cần lưu trữ những giá trị để sử dụng trong quá trình xử lý.

Một biến là một vùng lưu trữ có tên, được sử dụng để đại diện cho một giá trị trong chương trình.

Mỗi biến có một kiểu dữ liệu xác định.

Một số kiểu dữ liệu cơ bản trong C++:

- `int`: Số nguyên.
- `long long`: Số nguyên có phạm vi biểu diễn lớn hơn `int`.
- `float`: Số thực với độ chính xác đơn.
- `double`: Số thực với độ chính xác kép.
- `char`: Một ký tự.
- `bool`: Giá trị logic `true` hoặc `false`.
- `string`: Chuỗi ký tự.

Ngoài kiểu dữ liệu, chúng ta cần làm quen với các toán tử.

Toán tử là những ký hiệu được sử dụng để thực hiện phép toán trên các giá trị.

Ví dụ:

| Nhóm toán tử | Các toán tử |
|---|---|
| Số học | `+`, `-`, `*`, `/`, `%` |
| So sánh | `==`, `!=`, `<`, `>`, `<=`, `>=` |
| Logic | `&&`, `||`, `!` |
| Gán | `=`, `+=`, `-=`, `*=`, `/=` |
| Tăng giảm | `++`, `--` |

Một điểm cần đặc biệt chú ý là toán tử `%` trong C++ không hoàn toàn tương đương với quy ước modulo có số dư không âm mà chúng ta đã học trong toán học.

Trong C++, phần dư của phép chia số nguyên có dấu được xác định theo phép chia lấy thương về phía \(0\).

Ví dụ:

```cpp
cout << -5 % 3;
```

Kết quả là:

```text
-2
```

Trong khi đó, theo quy ước modulo toán học với modulo dương:

$$
-5\bmod3=1.
$$

Đây là một sự khác biệt quan trọng cần ghi nhớ khi chuyển những công thức toán học sang chương trình C++.

### 4.4. Câu lệnh điều kiện

Trong một chương trình, không phải lúc nào chúng ta cũng thực hiện các thao tác theo cùng một trình tự.

Đôi khi, chương trình cần đưa ra quyết định dựa trên một điều kiện.

Câu lệnh điều kiện cho phép chúng ta kiểm soát luồng thực thi của chương trình.

Trong C++, cấu trúc cơ bản là:

```cpp
if (condition) {
    // Statements
}
else {
    // Statements
}
```

Trong đó:

- `if` thực hiện một nhóm câu lệnh khi điều kiện đúng.
- `else` thực hiện một nhóm câu lệnh khi điều kiện sai.
- `condition` là biểu thức logic có giá trị đúng hoặc sai.

Ví dụ, chúng ta có thể sử dụng câu lệnh điều kiện để kiểm tra một số nguyên có chẵn hay không.

```cpp
if (n % 2 == 0) {
    cout << "Even";
}
else {
    cout << "Odd";
}
```

Ngoài `if` và `else`, chúng ta còn có thể sử dụng `else if` để kiểm tra nhiều điều kiện khác nhau.

### 4.5. Vòng lặp

Một trong những lợi ích quan trọng nhất của máy tính là khả năng thực hiện một thao tác nhiều lần.

Thay vì viết lại cùng một câu lệnh nhiều lần, chúng ta có thể sử dụng vòng lặp.

Trong C++, có ba cấu trúc vòng lặp thường gặp:

**Vòng lặp `for`**

Thường được sử dụng khi số lần lặp đã được xác định hoặc có thể biểu diễn bằng một điều kiện đếm.

```cpp
for (int i = 0; i < 5; i++) {
    cout << i << '\n';
}
```

**Vòng lặp `while`**

Tiếp tục thực hiện một nhóm câu lệnh khi điều kiện còn đúng.

```cpp
while (condition) {
    // Statements
}
```

**Vòng lặp `do while`**

Thực hiện nhóm câu lệnh ít nhất một lần trước khi kiểm tra điều kiện lặp.

```cpp
do {
    // Statements
} while (condition);
```

Vòng lặp là một thành phần đặc biệt quan trọng trong Competitive Programming vì nhiều thuật toán cần xử lý một lượng lớn phần tử hoặc lặp lại các bước tính toán.

### 4.6. Mảng

Khi làm việc với nhiều giá trị cùng loại, việc khai báo từng biến riêng biệt sẽ trở nên bất tiện.

Ví dụ, nếu cần lưu trữ \(100\) số nguyên, chúng ta không muốn phải tạo ra \(100\) biến riêng biệt.

Thay vào đó, chúng ta sử dụng mảng.

Mảng (Array) là một cấu trúc dữ liệu cho phép lưu trữ nhiều phần tử cùng kiểu dữ liệu trong một vùng nhớ liên tiếp.

Ví dụ:

```cpp
int a[5] = {3, 8, 2, 11, 5};
```

Mảng trên chứa năm phần tử.

Trong C++, chỉ số của mảng bắt đầu từ \(0\).

Vì vậy:

| Chỉ số | Giá trị |
|---|---:|
| `a[0]` | 3 |
| `a[1]` | 8 |
| `a[2]` | 2 |
| `a[3]` | 11 |
| `a[4]` | 5 |

Chúng ta có thể truy cập một phần tử thông qua chỉ số tương ứng.

Mảng là một trong những nền tảng quan trọng nhất trong việc xử lý dữ liệu và triển khai thuật toán.

Sau này, chúng ta sẽ tiếp tục mở rộng kiến thức này sang các cấu trúc dữ liệu khác như danh sách liên kết, ngăn xếp, hàng đợi và nhiều cấu trúc phức tạp hơn.

### 4.7. Những kiến thức tiếp theo

Ngoài các nội dung trên, C++ còn có nhiều thành phần quan trọng khác:

- Hàm (Functions).
- Chuỗi ký tự (Strings).
- Tham chiếu (References).
- Con trỏ (Pointers).
- Cấu trúc và kiểu dữ liệu tự định nghĩa.
- Mảng động và các cấu trúc dữ liệu trong STL.

Những nội dung này sẽ được giới thiệu và sử dụng tùy theo nhu cầu của các bài học tiếp theo.

Không nhất thiết phải học toàn bộ C++ trước khi bắt đầu Competitive Programming. Thay vào đó, chúng ta sẽ xây dựng kiến thức lập trình song song với việc nghiên cứu thuật toán.

---

## 5. Lộ trình kiến thức Competitive Programming

Sau khi có nền tảng C++ cơ bản, chúng ta sẽ tiếp tục mở rộng kiến thức về thuật toán và cấu trúc dữ liệu.

Đây không phải là một danh sách những chủ đề độc lập, mà là một lộ trình được xây dựng để các kiến thức mới có thể sử dụng những kiến thức đã học trước đó.

Một số nhóm nội dung chính bao gồm:

### 5.1. Thuật toán cơ bản

Đây là nhóm kiến thức giúp chúng ta làm quen với cách phân tích và xây dựng lời giải.

Các nội dung thường gặp:

- Tìm kiếm (Searching).
- Sắp xếp (Sorting).
- Kỹ thuật hai con trỏ (Two Pointers).
- Tìm kiếm nhị phân (Binary Search).
- Tham lam (Greedy Algorithms).

### 5.2. Cấu trúc dữ liệu

Cấu trúc dữ liệu (Data Structures) là cách tổ chức và lưu trữ dữ liệu để việc truy cập, cập nhật và xử lý trở nên hiệu quả.

Một số cấu trúc dữ liệu thường gặp:

- Mảng (Array).
- Danh sách liên kết (Linked List).
- Ngăn xếp (Stack).
- Hàng đợi (Queue).
- Hàng đợi ưu tiên (Priority Queue).
- Tập hợp và ánh xạ (Set and Map).
- Cây (Tree).
- Cây đoạn (Segment Tree).
- Cây Fenwick (Fenwick Tree).

### 5.3. Lý thuyết số

Lý thuyết số (Number Theory) nghiên cứu các tính chất của số nguyên.

Nhóm kiến thức này có mối liên hệ trực tiếp với phần Toán học đã học.

Một số nội dung:

- Số nguyên tố.
- Tính chia hết.
- Ước chung lớn nhất.
- Bội chung nhỏ nhất.
- Phân tích thừa số nguyên tố.
- Đồng dư modulo.
- Nghịch đảo modulo.
- Thuật toán Euclid.

### 5.4. Quy hoạch động

Quy hoạch động (Dynamic Programming) là một phương pháp giải bài toán bằng cách chia bài toán thành những bài toán con có cấu trúc liên quan, sau đó lưu lại kết quả để tránh tính toán lặp lại.

Đây là một trong những chủ đề quan trọng và thường có mức độ thử thách cao trong Competitive Programming.

### 5.5. Thuật toán đồ thị

Thuật toán đồ thị (Graph Algorithms) nghiên cứu cách xử lý những cấu trúc bao gồm đỉnh và cạnh.

Một số nội dung thường gặp:

- Duyệt đồ thị.
- Tìm kiếm theo chiều sâu (DFS).
- Tìm kiếm theo chiều rộng (BFS).
- Thành phần liên thông.
- Đường đi ngắn nhất.
- Cây khung nhỏ nhất.
- Các thuật toán trên đồ thị có trọng số.

Các chủ đề trên sẽ được giới thiệu theo từng giai đoạn, không yêu cầu người học phải biết trước toàn bộ kiến thức ngay từ tuần đầu tiên.

---

## 6. Tài liệu tham khảo

Trong quá trình học Competitive Programming, chúng ta sẽ sử dụng hai nguồn tài liệu chính.

Mỗi nguồn có mục đích khác nhau, vì vậy người học cần hiểu khi nào nên sử dụng nguồn nào.

### 6.1. C++ Fundamentals

**Tài liệu tham khảo:** [W3Schools — C++ Tutorial](https://www.w3schools.com/cpp/default.asp)

W3Schools cung cấp tài liệu giới thiệu những kiến thức cơ bản về C++.

Một số nội dung được đề cập:

- Cú pháp và cấu trúc chương trình.
- Biến và kiểu dữ liệu.
- Toán tử.
- Câu lệnh điều kiện.
- Vòng lặp.
- Hàm.
- Mảng và chuỗi ký tự.
- Con trỏ và tham chiếu.
- Các khái niệm cơ bản khác.

Đây là nguồn tham khảo phù hợp cho những người chưa quen với C++ hoặc cần ôn tập lại cú pháp và cách sử dụng ngôn ngữ.

Không nhất thiết phải đọc toàn bộ tài liệu theo thứ tự từ đầu đến cuối. Hãy ưu tiên những nội dung tương ứng với chương trình học hiện tại.

### 6.2. Competitive Programming Fundamentals

**Tài liệu tham khảo:** [CP-Algorithms](https://cp-algorithms.com/index.html)

CP-Algorithms là một tài liệu tham khảo chuyên sâu về thuật toán và cấu trúc dữ liệu thường được sử dụng trong Competitive Programming.

Một số nhóm nội dung chính:

- Thuật toán cơ bản.
- Cấu trúc dữ liệu.
- Số học và lý thuyết số.
- Quy hoạch động.
- Thuật toán đồ thị.
- Hình học tính toán.
- Các kỹ thuật và thuật toán nâng cao.

Khác với tài liệu giới thiệu C++, CP-Algorithms tập trung vào cách giải quyết bài toán.

Một bài viết trên CP-Algorithms thường có thể bao gồm:

- Mô tả bài toán.
- Ý tưởng thuật toán.
- Cơ sở toán học.
- Cách triển khai.
- Độ phức tạp thời gian và bộ nhớ.

Đây là nguồn tham khảo rất hữu ích khi chúng ta đã có nền tảng lập trình và muốn tìm hiểu sâu hơn về một thuật toán cụ thể.

**Lưu ý:** CP-Algorithms là tài liệu tra cứu thuật toán, không phải giáo trình nhập môn C++ dành cho người chưa từng lập trình. Vì vậy, người học nên xây dựng kiến thức lập trình cơ bản trước khi tiếp cận những bài viết có độ phức tạp cao.

### 6.3. Cách sử dụng tài liệu

Hai nguồn tài liệu trên phục vụ hai mục đích khác nhau:

| Nguồn | Mục đích sử dụng |
|---|---|
| W3Schools — C++ Tutorial | Học và tra cứu cú pháp, cách sử dụng C++ |
| CP-Algorithms | Nghiên cứu ý tưởng, tính chất và cách triển khai thuật toán |

Các tài liệu này mang tính chất tham khảo. Người học có thể lựa chọn nội dung phù hợp với trình độ hiện tại và sử dụng chúng trong quá trình tự học, luyện tập và giải quyết bài toán.

---

## 7. Lộ trình học tập tuần 1

Trong tuần đầu tiên, chúng ta sẽ tập trung vào việc làm quen với C++ và cách xây dựng những chương trình cơ bản.

Các nội dung được sắp xếp theo trình tự từ việc tương tác với chương trình đến việc điều khiển luồng thực thi và xử lý dữ liệu.

### 7.1. Nhập và xuất dữ liệu (Input/Output)

Tìm hiểu cách chương trình tiếp nhận dữ liệu đầu vào và đưa kết quả ra đầu ra.

Những kiến thức cần nắm:

- `cin` và `cout`.
- `scanf` và `printf` ở mức làm quen.
- Đọc nhiều giá trị.
- Xuất kết quả theo định dạng yêu cầu.
- Các ký tự xuống dòng và khoảng trắng.

### 7.2. Câu lệnh điều kiện (Conditional Statements)

Tìm hiểu cách chương trình đưa ra quyết định dựa trên các điều kiện logic.

Những kiến thức cần nắm:

- `if`.
- `else`.
- `else if`.
- Các toán tử so sánh.
- Các toán tử logic.
- Cách kết hợp nhiều điều kiện.

### 7.3. Vòng lặp (Loops)

Tìm hiểu cách thực hiện một nhóm thao tác nhiều lần mà không cần viết lại các câu lệnh tương ứng.

Những kiến thức cần nắm:

- `for`.
- `while`.
- `do while`.
- `break` và `continue`.
- Vòng lặp lồng nhau.
- Cách xác định điều kiện bắt đầu, kết thúc và cập nhật của vòng lặp.

### 7.4. Mảng (Arrays)

Tìm hiểu cách lưu trữ và truy cập nhiều giá trị cùng kiểu dữ liệu.

Những kiến thức cần nắm:

- Khai báo và khởi tạo mảng.
- Truy cập phần tử thông qua chỉ số.
- Duyệt mảng.
- Cập nhật giá trị.
- Tìm kiếm phần tử.
- Tính toán trên các phần tử của mảng.
- Mối liên hệ giữa mảng và vòng lặp.

Đây là những kiến thức nền tảng cần thiết trước khi chuyển sang các thuật toán xử lý dữ liệu phức tạp hơn.

---

## 8. Nền tảng thực hành

Các hoạt động luyện tập của chương trình được tổ chức trên Codeforces.

**Đường dẫn:** [VNMCOI Contest — Codeforces](https://vnmcoi.contest.codeforces.com/)

Các thành viên sử dụng tài khoản và mật khẩu đã được cấp để đăng nhập vào hệ thống.

Codeforces là một nền tảng hỗ trợ tổ chức các cuộc thi và hoạt động luyện tập lập trình. Hệ thống cung cấp những bài toán có dữ liệu đầu vào, đầu ra và bộ kiểm thử để đánh giá tính đúng đắn của chương trình.

Khi một chương trình được gửi lên hệ thống, chương trình sẽ được biên dịch và chạy trên những bộ kiểm thử tương ứng.

Một số kết quả đánh giá thường gặp:

- **Accepted (AC):** Chương trình vượt qua toàn bộ các bộ kiểm thử.
- **Wrong Answer (WA):** Chương trình chạy được nhưng kết quả không chính xác ở ít nhất một trường hợp kiểm thử.
- **Time Limit Exceeded (TLE):** Chương trình vượt quá giới hạn thời gian.
- **Memory Limit Exceeded (MLE):** Chương trình sử dụng vượt quá giới hạn bộ nhớ.
- **Compilation Error (CE):** Chương trình không thể biên dịch thành công.

Việc hiểu các trạng thái này sẽ giúp người học phân biệt lỗi về mặt thuật toán, lỗi trong quá trình hiện thực hóa và những vấn đề liên quan đến hiệu năng.
