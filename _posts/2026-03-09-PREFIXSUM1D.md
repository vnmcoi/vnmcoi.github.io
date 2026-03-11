---
layout: post
title:  "PREFIXSUM1D"
categories: [prefix_sum]
code: PREFIXSUM1D
src: PREFIXSUM1D.cpp
---

<!--more-->

# Lời giải trâu

Dễ thấy với mỗi truy vấn ta thực hiện vét từng đoạn một theo yêu cầu của truy vấn.

```cpp

#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e5 + 5;

int N, Q;
int A[mxN];

int main()
{
    ios::sync_with_stdio(0);
    cin.tie(0);

    cin >> N >> Q;
    for (int i = 1; i <= N; ++i)
    {
        cin >> A[i];
    }
    while (Q--)
    {
        int l, r;
        cin >> l >> r;
        long long ans = 0;
        for (int i = 1; i <= N; ++i)
        {
            ans += A[i];
        }
        cout << ans << '\n';
    }
    return 0;
}

```

Độ phức tạp thời gian: `O(Q x N)`. Với `N` và `Q` ở mức `10^5` thì chắc chắn sẽ bị quá thời gian nếu thời gian chạy được quy định là 1 giây.

# Lời giải chuẩn

Chúng ta phải tìm cách để tối ưu việc tính bằng cách giảm số lần duyệt mảng lại của mỗi truy vấn.

Trong đó chúng ta sẽ thấy để tính tổng của đoạn `[l; r]` thì chúng ta có thể tính bằng cách tính tổng của đoạn `[1; r]` và `[1; l - 1]` vì `[l; r] = [1; r] - [1; l - 1]`.

Vậy chúng ta gọi mảng `pref` là mảng tổng tiền tố (tức sẽ lưu tổng từ vị trí `1` đến `i` hay `pref[i] =` tổng của đoạn `[1; i]`).

Khi đó tổng của truy vấn `[l; r]` chính là `pref[r] - pref[l - 1]`.

Độ phức tạp thời gian:

- Tiền xử lý mảng `pref`: `O(N)`.
- Trả lời truy vấn: `O(1)`.

Tổng độ phức tạp: `O(N + Q)`. Hoàn toàn chạy trong thời gian 1 giây với `N` và `Q` tối đa là `10^5`.