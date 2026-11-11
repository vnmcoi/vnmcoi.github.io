Bài toán yêu cầu tìm số bước di chuyển ít nhất của quân mã từ ô góc trên bên trái $(1,1)$ đến tất cả các ô còn lại trên bàn cờ $n \times n$.

Ta có thể mô hình hóa bàn cờ thành một đồ thị hai chiều:

- Mỗi ô trên bàn cờ là một đỉnh.
- Hai đỉnh được nối với nhau nếu quân mã có thể di chuyển từ ô này sang ô kia trong một nước đi.

Vì mỗi nước đi của quân mã có trọng số bằng $1$, ta sử dụng thuật toán BFS (Breadth-First Search) để tìm khoảng cách ngắn nhất từ ô xuất phát đến tất cả các ô trên bàn cờ.

## Các hướng di chuyển của quân mã

Quân mã có thể di chuyển theo $8$ hướng:

$$ (\pm 2,\pm 1), \quad (\pm 1,\pm 2) $$

Ta lưu các hướng di chuyển này vào hai mảng `moveX` và `moveY`.

Với mỗi ô hiện tại $(x,y)$, ta lần lượt thử di chuyển theo cả $8$ hướng để xác định các ô tiếp theo mà quân mã có thể đi đến.

## Thuật toán BFS

Ta sử dụng:

- `vis[x][y]` để đánh dấu ô $(x,y)$ đã được duyệt.
- `dist[x][y]` để lưu số bước di chuyển ít nhất từ ô xuất phát đến ô $(x,y)$.
- Một hàng đợi `queue` để lưu các ô đang chờ được duyệt.

Đầu tiên, đánh dấu ô xuất phát $(1,1)$ đã được duyệt và đưa vào hàng đợi.

Sau đó, thực hiện BFS:

1. Lấy ô $(x,y)$ ở đầu hàng đợi và loại bỏ nó.
2. Thử cả $8$ hướng di chuyển của quân mã.
3. Nếu ô mới $(newX,newY)$ nằm trong phạm vi bàn cờ và chưa được duyệt:
   - Đánh dấu ô đó đã được duyệt.
   - Cập nhật khoảng cách:

$$ dist[newX][newY]=dist[x][y]+1 $$

\- Đưa ô mới vào hàng đợi.

Quá trình kết thúc khi hàng đợi rỗng. Khi đó, `dist[x][y]` chính là số bước di chuyển ít nhất từ ô $(1,1)$ đến ô $(x,y)$.

Cuối cùng, ta duyệt và in ma trận khoảng cách `dist`.

### Độ phức tạp

Gọi $n$ là kích thước bàn cờ.

- Thời gian: $O(n^2)$, vì có $n^2$ ô và mỗi ô được duyệt tối đa một lần, với $8$ hướng di chuyển.
- Bộ nhớ: $O(n^2)$, để lưu mảng đánh dấu, ma trận khoảng cách và hàng đợi BFS.

```cpp
#include <bits/stdc++.h>
using namespace std;

const int mxN = 1e3 + 5;

const int moveX[] = {-2, -2, -1, 1, 2, 2, 1, -1};
const int moveY[] = {-1, 1, 2, 2, 1, -1, -2, -2};

int N;
bitset<mxN> vis[mxN];
int dist[mxN][mxN];

bool check(int x, int y)
{
    return 1 <= x && x <= N && 1 <= y && y <= N && vis[x][y] == false;
}

void solve(void)
{
    cin >> N;
    queue<pair<int, int>> q;
    vis[1][1] = true;
    q.push(make_pair(1, 1));
    while (q.empty() == false)
    {
        int x = q.front().first;
        int y = q.front().second;
        q.pop();
        for (int i = 0; i <= 7; ++i)
        {
            int newX = x + moveX[i];
            int newY = y + moveY[i];
            if (check(newX, newY) == true)
            {
                vis[newX][newY] = true;
                dist[newX][newY] = dist[x][y] + 1;
                q.push(make_pair(newX, newY));
            }
        }
    }
    for (int i = 1; i <= N; ++i)
    {
        for (int j = 1; j <= N; ++j)
        {
            cout << dist[i][j] << ' ';
        }
        cout << '\n';
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