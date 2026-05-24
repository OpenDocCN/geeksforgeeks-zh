# 检查方向矩阵中给定单元之间是否存在有效路径

> 原文：[https://www.geeksforgeeks.org/check-if-a-valid-path-exists-between-given-cells-in-a-directional-matrix/](https://www.geeksforgeeks.org/check-if-a-valid-path-exists-between-given-cells-in-a-directional-matrix/)

给定一个`N×M`矩阵。矩阵的每个单元都有一个指向下一个单元的数值。`matrix[i][j]`的值可以是：

*   **1** 表示去右边的单元（即从`matrix[i][j]`到`matrix[i][j + 1]`）。
*   **2** 表示去左边的单元（即从`matrix[i][j]`到`matrix[i][j - 1]`）。
*   **3** 表示转到下单元（即从`matrix[i][j]`到`matrix[i + 1][j]`）。
*   **4** 表示转到上层单元（即从`matrix[i][j]`转到`matrix[i - 1][j]`）。

给出源单元格`(x1, y1)`和目的地单元格`(x2, y2)`。任务是找出给定源单元格和目标单元格之间是否存在路径。

**示例**：

> **输入**：`matrix[][] = {{3, 2, 2, 2}, {3, 4, 2, 3}, {1, 3, 4, 4}, {2, 1, 1, 2}, {4, 4, 3, 3}}`，源单元格 = `{0, 3}`，目标单元格 = `{3, 1}`
> **输出**：是
>
> | 3 | 2 | 2 | 2 |
> |---|---|---|---|
> | 3 | 4 | 2 | 3 |
> | 1 | 3 | 4 | 4 |
> | 2 | 1 | 1 | 2 |
> | 4 | 4 | 3 | 3 |
>
> **说明**：从单元格`(0, 3)`开始，按照基于方向规则的路径。按照以下顺序遍历单元格：`(0, 3) -> (0, 2) -> (0, 1) -> (0, 0) -> (1, 0) -> (2, 0) -> (2, 1) -> (3, 1)`，这就是目的地。
>
> **输入**：`matrix[][] = {{1, 4, 3}, {2, 3, 2}, {4, 1, 4}}`，源单元格 = `{1, 1}`，目标单元格 = `{0, 3}`
> **输出**：否
>
> | 1 | 4 | 3 |
> |---|---|---|
> | 2 | 3 | 2 |
> | 4 | 1 | 4 |
>
> **说明**：从单元格`(1, 1)`开始，按照基于方向规则的路径。遍历单元格为：`(1, 1) -> (2, 1) -> (2, 2) -> (1, 2) -> (1, 1)`，这里再次访问源单元格，因此在任何情况下都不访问目标单元格。

**方法**：可以使用 [DFS](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/) 或者 [BFS](https://www.geeksforgeeks.org/breadth-first-traversal-for-a-graph/) 解决任务。

*   可以观察到要遵循的路径是固定的，我们需要根据指定的方向规则遍历矩阵。
*   从源单元格启动 DFS 或 BFS，并根据上述方向规则移动。
*   如果到达目标小区，则找到一条有效的路径。
*   如果某个访问的小区再次重访或者当前小区的索引超出了范围，则该路径无法到达目的小区，否则继续。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check whether a valid path
// exists or not
bool uniquepath(vector<vector<int> >& matrix, int curr_x,
                int curr_y, int dest_x, int dest_y,
                vector<vector<bool> >& visited)
{
    // Check if destination cell is reached
    if (curr_x == dest_x && curr_y == dest_y)
        return true;

    // Base Cases
    if (!(curr_x >= 0 && curr_x < matrix.size()
          && curr_y >= 0 && curr_y < matrix[0].size()))
        return false;

    // Check whether a visited cell is
    // re-visited again
    if (visited[curr_x][curr_y] == true)
        return false;

    // Mark current cell as visited
    visited[curr_x][curr_y] = true;

    // Moving based on direction rule
    if (matrix[curr_x][curr_y] == 1)
        return uniquepath(matrix, curr_x, curr_y + 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 2)
        return uniquepath(matrix, curr_x, curr_y - 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 3)
        return uniquepath(matrix, curr_x + 1, curr_y,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 4)
        return uniquepath(matrix, curr_x - 1, curr_y,
                          dest_x, dest_y, visited);
}

// Driver code
int main()
{
    vector<vector<int> > matrix = { { 3, 2, 2, 2 },
                                    { 3, 4, 2, 3 },
                                    { 1, 3, 4, 4 },
                                    { 2, 1, 1, 2 },
                                    { 4, 4, 1, 2 } };
    int start_x = 0, start_y = 3;
    int dest_x = 3, dest_y = 1;
    int n = matrix.size();
    int m = matrix[0].size();
    vector<vector<bool> > visited(
        n,
        vector<bool>(m, false));
    if (uniquepath(matrix, start_x, start_y,
                   dest_x, dest_y,
                   visited))
        cout << "Yes";
    else
        cout << "No";
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to check whether a valid path
// exists or not
static boolean uniquepath(int[][]matrix, int curr_x,
                          int curr_y, int dest_x,
                          int dest_y, boolean[][] visited)
{

    // Check if destination cell is reached
    if (curr_x == dest_x && curr_y == dest_y)
        return true;

    // Base Cases
    if (!(curr_x >= 0 && curr_x < matrix.length &&
          curr_y >= 0 && curr_y < matrix[0].length))
        return false;

    // Check whether a visited cell is
    // re-visited again
    if (visited[curr_x][curr_y] == true)
        return false;

    // Mark current cell as visited
    visited[curr_x][curr_y] = true;

    // Moving based on direction rule
    if (matrix[curr_x][curr_y] == 1)
        return uniquepath(matrix, curr_x, curr_y + 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 2)
        return uniquepath(matrix, curr_x, curr_y - 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 3)
        return uniquepath(matrix, curr_x + 1, curr_y,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x][curr_y] == 4)
        return uniquepath(matrix, curr_x - 1, curr_y,
                          dest_x, dest_y, visited);

    return false;
}

// Driver code
public static void main(String[] args)
{
    int[][] matrix = { { 3, 2, 2, 2 },
                       { 3, 4, 2, 3 },
                       { 1, 3, 4, 4 },
                       { 2, 1, 1, 2 },
                       { 4, 4, 1, 2 } };

    int start_x = 0, start_y = 3;
    int dest_x = 3, dest_y = 1;
    int n = matrix.length;
    int m = matrix[0].length;

    boolean[][] visited = new boolean[n][m];
    if (uniquepath(matrix, start_x, start_y,
                   dest_x, dest_y, visited))
        System.out.print("Yes");
    else
        System.out.print("No");
}
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# python program for the above approach

# Function to check whether a valid path
# exists or not
def uniquepath(matrix, curr_x, curr_y, dest_x, dest_y, visited):

    # Check if destination cell is reached
    if (curr_x == dest_x and curr_y == dest_y):
        return True

    # Base Cases
    if (not(curr_x >= 0 and curr_x < len(matrix) and curr_y >= 0 and curr_y < len(matrix[0]))):
        return False

    # Check whether a visited cell is
    # re-visited again
    if (visited[curr_x][curr_y] == True):
        return False

    # Mark current cell as visited
    visited[curr_x][curr_y] = True

    # Moving based on direction rule
    if (matrix[curr_x][curr_y] == 1):
        return uniquepath(matrix, curr_x, curr_y + 1, dest_x, dest_y, visited)
    elif (matrix[curr_x][curr_y] == 2):
        return uniquepath(matrix, curr_x, curr_y - 1, dest_x, dest_y, visited)
    elif (matrix[curr_x][curr_y] == 3):
        return uniquepath(matrix, curr_x + 1, curr_y, dest_x, dest_y, visited)
    elif (matrix[curr_x][curr_y] == 4):
        return uniquepath(matrix, curr_x - 1, curr_y, dest_x, dest_y, visited)

# Driver code
if __name__ == "__main__":

    matrix = [[3, 2, 2, 2],
              [3, 4, 2, 3],
              [1, 3, 4, 4],
              [2, 1, 1, 2],
              [4, 4, 1, 2]
              ]
    start_x = 0
    start_y = 3
    dest_x = 3
    dest_y = 1
    n = len(matrix)
    m = len(matrix[0])
    visited = [[False for _ in range(m)] for _ in range(n)]
    if (uniquepath(matrix, start_x, start_y, dest_x, dest_y, visited)):
        print("Yes")
    else:
        print("No")

    # This code is contributed by rakeshsahni
```

## C#

```
// C# program for the above approach
using System;

public class GFG{

// Function to check whether a valid path
// exists or not
static bool uniquepath(int[,]matrix, int curr_x,
                          int curr_y, int dest_x,
                          int dest_y, bool[,] visited)
{

    // Check if destination cell is reached
    if (curr_x == dest_x && curr_y == dest_y)
        return true;

    // Base Cases
    if (!(curr_x >= 0 && curr_x < matrix.GetLength(0) &&
          curr_y >= 0 && curr_y < matrix.GetLength(1)))
        return false;

    // Check whether a visited cell is
    // re-visited again
    if (visited[curr_x,curr_y] == true)
        return false;

    // Mark current cell as visited
    visited[curr_x,curr_y] = true;

    // Moving based on direction rule
    if (matrix[curr_x,curr_y] == 1)
        return uniquepath(matrix, curr_x, curr_y + 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x,curr_y] == 2)
        return uniquepath(matrix, curr_x, curr_y - 1,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x,curr_y] == 3)
        return uniquepath(matrix, curr_x + 1, curr_y,
                          dest_x, dest_y, visited);
    else if (matrix[curr_x,curr_y] == 4)
        return uniquepath(matrix, curr_x - 1, curr_y,
                          dest_x, dest_y, visited);

    return false;
}

// Driver code
public static void Main(String[] args)
{
    int[,] matrix = { { 3, 2, 2, 2 },
                       { 3, 4, 2, 3 },
                       { 1, 3, 4, 4 },
                       { 2, 1, 1, 2 },
                       { 4, 4, 1, 2 } };

    int start_x = 0, start_y = 3;
    int dest_x = 3, dest_y = 1;
    int n = matrix.GetLength(0);
    int m = matrix.GetLength(1);

    bool[,] visited = new bool[n,m];
    if (uniquepath(matrix, start_x, start_y,
                   dest_x, dest_y, visited))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```
<script>
// Javascript program for the above approach

// Function to check whether a valid path
// exists or not
function uniquepath(matrix, curr_x, curr_y, dest_x, dest_y, visited)
{

  // Check if destination cell is reached
  if (curr_x == dest_x && curr_y == dest_y) return true;

  // Base Cases
  if (
    !(
      curr_x >= 0 &&
      curr_x < matrix.length &&
      curr_y >= 0 &&
      curr_y < matrix[0].length
    )
  )
    return false;

  // Check whether a visited cell is
  // re-visited again
  if (visited[curr_x][curr_y] == true) return false;

  // Mark current cell as visited
  visited[curr_x][curr_y] = true;

  // Moving based on direction rule
  if (matrix[curr_x][curr_y] == 1)
    return uniquepath(matrix, curr_x, curr_y + 1, dest_x, dest_y, visited);
  else if (matrix[curr_x][curr_y] == 2)
    return uniquepath(matrix, curr_x, curr_y - 1, dest_x, dest_y, visited);
  else if (matrix[curr_x][curr_y] == 3)
    return uniquepath(matrix, curr_x + 1, curr_y, dest_x, dest_y, visited);
  else if (matrix[curr_x][curr_y] == 4)
    return uniquepath(matrix, curr_x - 1, curr_y, dest_x, dest_y, visited);
}

// Driver code

let matrix = [
  [3, 2, 2, 2],
  [3, 4, 2, 3],
  [1, 3, 4, 4],
  [2, 1, 1, 2],
  [4, 4, 1, 2],
];
let start_x = 0,
  start_y = 3;
let dest_x = 3,
  dest_y = 1;
let n = matrix.length;
let m = matrix[0].length;

let visited = new Array(n).fill(0).map(() => new Array(m).fill(false));
if (uniquepath(matrix, start_x, start_y, dest_x, dest_y, visited))
  document.write("Yes");
else document.write("No");

// This code is contributed by gfgking.
</script>
```

`Output`

```
Yes
```

`时间复杂度` : `O(n*m)`
`辅助空间` : `O(n*m)`