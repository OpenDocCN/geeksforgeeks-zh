# 检查给定的二进制矩阵中是否有 T 个连续的 0 块

> 原文: [https://www.geeksforgeeks.org/check-if-there-are-t-number-of-continuous-of-blocks-of-0s-or-not-in-given-binary-matrix/](https://www.geeksforgeeks.org/check-if-there-are-t-number-of-continuous-of-blocks-of-0s-or-not-in-given-binary-matrix/)

给定尺寸为 `M*N` 的二进制矩阵 `mat[][]`，任务是检查是否存在 `T` 连续块的 `0s` 和至少 `2 * max(M, N)` 值为 `0s` 的单元格。如果发现为真，则打印 `是`。否则，打印 `否`。

`T` 定义为 `N` 和 `M` 的 `GCD`。连续块被定义为通过行方向、列方向或对角线方向的连续拉伸。

## 示例

**输入:** `N = 3`，`M = 4`，`mat[][] = { {1, 0, 0}, {1, 1, 0}, {0, 0, 0}, {0, 0, 1} }`
**输出:** 是
**说明:** 矩阵正好有 8 个单元格，0 值等于 `2*max(N, M))`，有 1 个连续点等于 `N` 和 `M` 的 `GCD`。

**输入:** `N = 3`，`M = 3`，`mat[][] = {{0, 0, 1}, {1, 1, 1}, {0, 0, 1}}`
**输出:** 否

## 方法

想法是计算值为 `0` 的单元数量，如果满足条件，则找到 `M` 和 `N` 的最大公约数，并执行深度优先搜索以找到值为 `0` 的连接组件数量。按照以下步骤解决问题:

*   初始化一个变量，称 `black` 为 `0`，用数值 `0` 计数细胞数。
*   如果 `black` 小于等于 `2 * max(M, N)`，则打印 `否` 并从函数返回。
*   初始化一个变量，将 `black_spots` 设为 `0` 来计算连续点的数量。
*   使用变量 `i` 迭代范围 `[0, M]`，使用变量 `j` 迭代范围 `[0, N]`，如果当前单元格 `visited[i][j]` 为 `假`，如果 `mat[i][j]` 为 `0`，则执行 `DFS`。
*   执行上述步骤后，如果 `black_spots` 的值大于 `gcd(M, N)`，则打印 `是`。否则，打印 `否`。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;
const long long M = 1e9 + 7;

// Stores the moves in the matrix
vector<pair<int, int> > directions
    = { { 0, 1 }, { -1, 0 }, { 0, -1 },
        { 1, 0 }, { 1, 1 }, { -1, -1 },
        { -1, 1 }, { 1, -1 } };

// Function to find if the current cell
// lies in the matrix or not
bool isInside(int i, int j, int N, int M)
{
    if (i >= 0 && i < N
        && j >= 0 && j < M) {
        return true;
    }
    return false;
}

// Function to perform the DFS Traversal
void DFS(vector<vector<int> > mat, int N,
         int M, int i, int j,
         vector<vector<bool> >& visited)
{
    if (visited[i][j] == true) {
        return;
    }

    visited[i][j] = true;

    // Iterate over the direction vector
    for (auto it : directions) {
        int I = i + it.first;
        int J = j + it.second;
        if (isInside(I, J, N, M)) {
            if (mat[I][J] == 0) {
                // DFS Call
                DFS(mat, N, M, I,
                    J, visited);
            }
        }
    }
}

// Function to check if it satisfy the
// given criteria or not
void check(int N, int M,
           vector<vector<int> >& mat)
{
    // Keeps the count of cell having
    // value as 0
    int black = 0;

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            if (mat[i][j] == 0) {
                black++;
            }
        }
    }

    // If condition doesn't satisfy
    if (black < 2 * (max(N, M))) {
        cout << "NO" << endl;
        return;
    }

    vector<vector<bool> > visited;

    for (int i = 0; i < N; i++) {
        vector<bool> temp;
        for (int j = 0; j < M; j++) {
            temp.push_back(false);
        }
        visited.push_back(temp);
    }

    // Keeps the track of unvisted cell
    // having values 0
    int black_spots = 0;

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            if (visited[i][j] == false
                && mat[i][j] == 0) {
                // Increasing count of
                // black_spot
                black_spots++;
                DFS(mat, N, M, i, j, visited);
            }
        }
    }

    // Find the GCD of N and M
    int T = __gcd(N, M);

    // Print the result
    cout << (black_spots >= T ? "Yes" : "No");
}

// Driver Code
int main()
{
    int N = 3, M = 3;
    vector<vector<int> > mat
        = { { 0, 0, 1 }, { 1, 1, 1 }, { 0, 0, 1 } };

    check(M, N, mat);

    return 0;
}
```

## Python 3

```python
# python program for the above approach
import math

M = 1000000000 + 7

# Stores the moves in the matrix
directions = [[0, 1], [-1, 0], [0, -1],
              [1, 0], [1, 1], [-1, -1],
              [-1, 1], [1, -1]]

# Function to find if the current cell
# lies in the matrix or not
def isInside(i, j, N, M):
    if (i >= 0 and i < N and j >= 0 and j < M):
        return True
    return False

# Function to perform the DFS Traversal
def DFS(mat, N, M, i, j, visited):
    if (visited[i][j] == True):
        return

    visited[i][j] = True

    # Iterate over the direction vector
    for it in directions:
        I = i + it[0]
        J = j + it[1]
        if (isInside(I, J, N, M)):
            if (mat[I][J] == 0):
                # DFS Call
                DFS(mat, N, M, I, J, visited)

# Function to check if it satisfy the
# given criteria or not
def check(N, M, mat):
    # Keeps the count of cell having
    # value as 0
    black = 0

    for i in range(0, N):
        for j in range(0, M):
            if (mat[i][j] == 0):
                black += 1

    # If condition doesn't satisfy
    if (black < 2 * (max(N, M))):
        print("NO")
        return

    visited = []
    for i in range(0, N):
        temp = []
        for j in range(0, M):
            temp.append(False)
        visited.append(temp)

    # Keeps the track of unvisted cell
    # having values 0
    black_spots = 0

    for i in range(0, N):
        for j in range(0, M):
            if (visited[i][j] == False and mat[i][j] == 0):
                # Increasing count of
                # black_spot
                black_spots += 1
                DFS(mat, N, M, i, j, visited)

    # Find the GCD of N and M
    T = math.gcd(N, M)

    # Print the result
    if black_spots >= T:
        print("Yes")
    else:
        print("No")

# Driver Code
if __name__ == "__main__":
    N = 3
    M = 3
    mat = [[0, 0, 1], [1, 1, 1], [0, 0, 1]]

    check(M, N, mat)

# This code is contributed by rakeshsahni
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach
let M = 1e9 + 7;

// Stores the moves in the matrix
let directions = [
  [0, 1],
  [-1, 0],
  [0, -1],
  [1, 0],
  [1, 1],
  [-1, -1],
  [-1, 1],
  [1, -1],
];

// Function to find if the current cell
// lies in the matrix or not
function isInside(i, j, N, M) {
  if (i >= 0 && i < N && j >= 0 && j < M) {
    return true;
  }
  return false;
}

// Function to perform the DFS Traversal
function DFS(mat, N, M, i, j, visited) {
  if (visited[i][j] == true) {
    return;
  }

  visited[i][j] = true;

  // Iterate over the direction vector
  for (let it of directions) {
    let I = i + it[0];
    let J = j + it[1];
    if (isInside(I, J, N, M)) {
      if (mat[I][J] == 0) {
        // DFS Call
        DFS(mat, N, M, I, J, visited);
      }
    }
  }
}

// Function to check if it satisfy the
// given criteria or not
function check(N, M, mat) {
  // Keeps the count of cell having
  // value as 0
  let black = 0;

  for (let i = 0; i < N; i++) {
    for (let j = 0; j < M; j++) {
      if (mat[i][j] == 0) {
        black++;
      }
    }
  }

  // If condition doesn't satisfy
  if (black < 2 * Math.max(N, M)) {
    document.write("NO<br>");
    return;
  }

  let visited = [];

  for (let i = 0; i < N; i++) {
    let temp = [];
    for (let j = 0; j < M; j++) {
      temp.push(false);
    }
    visited.push(temp);
  }

  // Keeps the track of unvisited cell
  // having values 0
  let black_spots = 0;

  for (let i = 0; i < N; i++) {
    for (let j = 0; j < M; j++) {
      if (visited[i][j] == false && mat[i][j] == 0) {
        // Increasing count of
        // black_spot
        black_spots++;
        DFS(mat, N, M, i, j, visited);
      }
    }
  }

  // Find the GCD of N and M
  let T = __gcd(N, M);

  // Print the result
  console.log(black_spots >= T ? "Yes" : "No");
}

// Driver Code
let N = 3;
M = 3;
let mat = [
  [0, 0, 1],
  [1, 1, 1],
  [0, 0, 1],
];

check(M, N, mat);

// This code is contributed by gfgking.
</script>
```

**输出:**

```
NO
```

**时间复杂度:** `O(N*M)`
**辅助空间:** `O(N*M)`