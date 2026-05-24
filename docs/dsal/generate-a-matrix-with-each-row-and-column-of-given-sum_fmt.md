# 生成给定总和的每行每列的矩阵

> 原文：[https://www.geeksforgeeks.org/generate-a-matrix-with-each-row-and-column-of-given-sum/](https://www.geeksforgeeks.org/generate-a-matrix-with-each-row-and-column-of-given-sum/)

给定两个尺寸分别为 `N` 和 `M` 的数组 `row[]` 和 `col[]`，任务是构建尺寸为 `N × M` 的矩阵，使得每第 `i` 行中矩阵元素的和为 `row[i]`，每第 `j` 列中矩阵元素的和为 `col[j]`。

**示例：**

> **输入：** `row[] = {5, 7, 10}`，`col[] = {8, 6, 8}`
> **输出：** `{{0, 5, 0}, {6, 1, 0}, {2, 0, 8}}`
> **解释：**
> 行 1 的和等于 5，列 1 的和等于 8
> 行 2 的和等于 7，列 2 的和等于 6
> 行 3 的和等于 10，列 3 的和等于 8
>
> **输入：** `row[] = {1, 0}`，`col[] = {1}`
> **输出：** `{{1}, {0}}`
> **解释：**
> 行 1 的和等于 1，列 1 的和等于 1
> 行 2 的和等于 0

**方法：** 解决这个问题最简单的方法就是使用贪婪方法。按照以下步骤解决此问题：

*   初始化一个具有尺寸 `N × M` 的矩阵。
*   按照以下方式开始填充矩阵的每个单元格 `(i, j)`：
    *   对于每个单元格 `(i, j)`，选择 `row[i]`、`col[j]` 的最小值，并将其放在单元格 `(i, j)` 处。
    *   从 `row[i]` 和 `col[j]` 中减去这个最小值。
*   完成上述步骤后，打印形成的矩阵。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to generate a matrix with
// sum of each row equal to sum of r[]
// and sum of each column equal to sum of c[]
vector<vector<int> > restoreGem(
    vector<int>& r, vector<int>& c)
{
    // Initialize a matrix
    vector<vector<int> > dp(r.size(),
                            vector<int>(c.size(), 0));

    // Traverse each cell (i, j) of the matrix
    for (int i = 0; i < r.size(); i++) {
        for (int j = 0; j < c.size(); j++) {

            // Assign the minimum of the
            // row or column value
            int m = min(r[i], c[j]);
            dp[i][j] = m;

            // Subtract the minimum from
            // both row and column sum
            r[i] -= m;
            c[j] -= m;
        }
    }

    return dp;
}

void printMatrix(vector<vector<int> > ans,
                 int N, int M)
{

    // Print the matrix obtained
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            cout << ans[i][j] << " ";
        }
        cout << endl;
    }
}

// Driver Code
int main()
{
    vector<int> rowSum = { 5, 7, 10 };
    vector<int> colSum = { 8, 6, 8 };

    vector<vector<int> > ans
        = restoreGem(rowSum, colSum);

    printMatrix(ans, rowSum.size(),
                colSum.size());
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
class GFG
{

// Function to generate a matrix with
// sum of each row equal to sum of r[]
// and sum of each column equal to sum of c[]
static int[][] restoreGem(int[] r, int[] c)
{

    // Initialize a matrix
    int[][] dp = new int[r.length][c.length];

    // Traverse each cell (i, j) of the matrix
    for (int i = 0; i < r.length; i++)
    {
        for (int j = 0; j < c.length; j++)
        {

            // Assign the minimum of the
            // row or column value
            int m = Math.min(r[i], c[j]);
            dp[i][j] = m;

            // Subtract the minimum from
            // both row and column sum
            r[i] -= m;
            c[j] -= m;
        }
    }
    return dp;
}

static void printMatrix(int[][] ans,
                 int N, int M)
{

    // Print the matrix obtained
    for (int i = 0; i < N; i++)
    {
        for (int j = 0; j < M; j++)
        {
            System.out.print(ans[i][j] + " ");
        }
        System.out.println();
    }
}

// Driver Code
public static void main(String[] args)
{
    int[] rowSum = { 5, 7, 10 };
    int[] colSum = { 8, 6, 8 };

    int[][] ans
        = restoreGem(rowSum, colSum);

    printMatrix(ans, rowSum.length,
                colSum.length);
}
}

// This code is contributed by susmitakundugoaldanga.
```

## C#

```csharp
// C# program for the above approach
using System;
public class GFG
{

// Function to generate a matrix with
// sum of each row equal to sum of r[]
// and sum of each column equal to sum of c[]
static int[,] restoreGem(int[] r, int[] c)
{

    // Initialize a matrix
    int[,] dp = new int[r.Length, c.Length];

    // Traverse each cell (i, j) of the matrix
    for (int i = 0; i < r.Length; i++)
    {
        for (int j = 0; j < c.Length; j++)
        {

            // Assign the minimum of the
            // row or column value
            int m = Math.Min(r[i], c[j]);
            dp[i,j] = m;

            // Subtract the minimum from
            // both row and column sum
            r[i] -= m;
            c[j] -= m;
        }
    }
    return dp;
}

static void printMatrix(int[,] ans,
                 int N, int M)
{

    // Print the matrix obtained
    for (int i = 0; i < N; i++)
    {
        for (int j = 0; j < M; j++)
        {
            Console.Write(ans[i, j] + " ");
        }
        Console.WriteLine();
    }
}

// Driver Code
public static void Main(String[] args)
{
    int[] rowSum = { 5, 7, 10 };
    int[] colSum = { 8, 6, 8 };

    int[,] ans
        = restoreGem(rowSum, colSum);
    printMatrix(ans, rowSum.Length,
                colSum.Length);
}
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>
// javascript program of the above approach

// Function to generate a matrix with
// sum of each row equal to sum of r[]
// and sum of each column equal to sum of c[]
function restoreGem(r, c)
{

    // Initialize a matrix
    let dp = new Array(r.length);

    // Loop to create 2D array using 1D array
    for (var i = 0; i < dp.length; i++) {
        dp[i] = new Array(2);
    }

    // Traverse each cell (i, j) of the matrix
    for (let i = 0; i < r.length; i++)
    {
        for (let j = 0; j < c.length; j++)
        {

            // Assign the minimum of the
            // row or column value
            let m = Math.min(r[i], c[j]);
            dp[i][j] = m;

            // Subtract the minimum from
            // both row and column sum
            r[i] -= m;
            c[j] -= m;
        }
    }
    return dp;
}

function printMatrix(ans, N, M)
{

    // Print the matrix obtained
    for (let i = 0; i < N; i++)
    {
        for (let j = 0; j < M; j++)
        {
            document.write(ans[i][j] + " ");
        }
        document.write("<br/>");
    }
}

    // Driver Code

    let rowSum = [ 5, 7, 10 ];
    let colSum = [ 8, 6, 8 ];

    let ans
        = restoreGem(rowSum, colSum);

    printMatrix(ans, rowSum.length,
                colSum.length);

</script>
```

**输出：**

```
5 0 0 
3 4 0 
0 2 8
```

**时间复杂度：** `O(N×M)`
**辅助空间：** `O(N×M)`