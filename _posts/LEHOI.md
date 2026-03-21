---
layout: post
title:  "LEHOI"
categories: []
code: LEHOI
src: LEHOI.cpp
---

<!--more-->

# Subtask 1

Quay lui ghép cặp các phần tử có thể.

# Subtask 2

Vì phần trăm giảm giá là `0` nên chúng ta tham lam ưu tiên các cặp có ba phần tử để được giảm giá nhiều phần tử nhất.

Tư tưởng một: Tại đây thì ta có thể thấy chúng ta sẽ ưu tiên ghép các phần tử sao cho chênh lệch giữa nhỏ nhất và lớn nhất là ít nhất có thể hay có thể nói là làm cho phần tử bé nhất trong bộ ba phải là lớn nhất để ghép cặp tối ưu.

# Subtask 3 và 4

Dễ thấy chúng ta sẽ phải thực hiện quy hoạch động vì có rất nhiều cấu hình cần xét nếu chúng ta thực hiện tham lam.

Tư tưởng hai: Chúng ta không bao giờ cần ghép nhóm có nhiều hơn ba phần tử vì dù có nhiều hơn chúng ta cũng không được khuyến mãi. Nên thay vì đó chúng ta chỉ cần xét điều kiện là ghép nhóm có một, hai, ba phần tử.

Gọi `f[i]` là giá trị nhỏ nhất cần dùng để thuê đến thiết bị thứ `i`.

Trường hợp cơ sở:

- `f[0] = 0`. Vì để thuê `0` thiết bị thì ta không tốn đồng nào.

Công thức quy hoạch động:

- `f[i] = min(f[i - 3] + giá trị khi bốc 3 phần tử, f[i - 2] + giá trị khi bốc 2 phần tử * (100 - q) / 100, f[i - 1] + giá trị khi bốc 1 phần tử * (100 - q) / 100)`.