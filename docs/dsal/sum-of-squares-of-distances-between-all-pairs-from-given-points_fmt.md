# 给定点所有对之间距离的平方和

> 原文：[https://www.geeksforgeeks.org/sum-of-squares-of-distances-between-all-pairs-from-given-points/](https://www.geeksforgeeks.org/sum-of-squares-of-distances-between-all-pairs-from-given-points/)

给定一个由 **XY 平面**上的 **N** 点的坐标组成的数组 `arr[][]`，任务是找出所有对点之间的平方距离之和，即 `(X_i–X_j)^2+(Y_i–Y_j)^2`。

## 示例

> **输入:** `arr[][] = {{1, 1}, {-1, -1}, {1, -1}, {-1, 1}}`
> **输出:** 32
> **说明:**
> 距离第 1 点 `(1, 1)` 距离第 2、第 3 和第 4 点分别为 8、4 和 4。
> 第 2 点与第 3 点和第 4 点的距离分别为 4 和 4。
> 第 3 点与第 4 点的距离为 8。
> 因此，总距离= (8 + 4 + 4) + (4 + 4) + (8) = 32
>
> **输入:** `arr[][] = {{1, 1}, {1, 1}, {0, 0}}`
> **输出:** 4
> **说明:**
> 第 1 点到第 2 和第 3 点的距离分别为 0 和 2。
> 第 2 点与第 3 点的距离为 2。
> 因此，总距离= (0 + 2) + (2) = 4

## 天真方法

解决问题最简单的方法是生成给定数组 `arr[][]` 的所有可能的不同对，并计算所有对点 `(X_i, Y_i)` 和 `(X_j, Y_j)` 之间距离的平方和，即 `(X_i–X_j)^2 + (Y_i–Y_j)^2`。

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(1)`

## 高效方法

对上述方法进行优化，思路是将距离平方和重新分组，拆分为两个和。按照以下步骤解决问题:

*   初始化变量，比如 `xq`、`yq`、`xs` 和 `ys`。
*   初始化一个变量，比如说 `res`，用 `0` 来存储结果和。
*   遍历给定的数组，对于每个点 `{x, y}`，执行以下步骤:
    *   将变量 `res` 中 `(i * x^2 + i * y^2)` 的值相加，对应平方距离的相加。
    *   将 `(xq - 2 * xs * a)` 和 `(yq - 2 * ys * b)` 加到 `res` 上，以抵消 `(a - b)^2` 扩展中 `2 * X * Y` 的效果。
    *   将值 `a^2` 和 `b^2` 分别添加到变量 `xq` 和 `yq` 中。
    *   将值 `a` 和 `b` 分别添加到变量 `xs` 和 `ys` 中。
    *   将数值 `xs` 和 `yq` 分别加到变量 `a^2` 和 `b^2` 中。
*   完成上述步骤后，打印 `res` 的值作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of squares
// of distance between all distinct pairs
void findSquareSum(
    int Coordinates[][2], int N)
{
    long long xq = 0, yq = 0;
    long long xs = 0, ys = 0;

    // Stores final answer
    long long res = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {
        int a, b;

        a = Coordinates[i][0];
        b = Coordinates[i][1];

        res += xq;
        res -= 2 * xs * a;

        // Adding the effect of this
        // point for all the previous
        // x - points
        res += i * (long long)(a * a);

        // Temporarily add the
        // square of x-coordinate
        xq += a * a;
        xs += a;
        res += yq;
        res -= 2 * ys * b;
        res += i * (long long)b * b;

        // Add the effect of this point
        // for all the previous y - points
        yq += b * b;
        ys += b;
    }

    // Print the desired answer
    cout << res;
}

// Driver Code
int main()
{
    int arr[][2] = { { 1, 1 },
                     { -1, -1 },
                     { 1, -1 },
                     { -1, 1 } };
    int N = sizeof(arr) / sizeof(arr[0]);
    findSquareSum(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.util.*;
class GFG
{

  // Function to find the sum of squares
  // of distance between all distinct pairs
  static void findSquareSum(
    int Coordinates[][], int N)
  {
    long xq = 0, yq = 0;
    long xs = 0, ys = 0;

    // Stores final answer
    long res = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {
      int a, b;

      a = Coordinates[i][0];
      b = Coordinates[i][1];

      res += xq;
      res -= 2 * xs * a;

      // Adding the effect of this
      // point for all the previous
      // x - points
      res += i * (long)(a * a);

      // Temporarily add the
      // square of x-coordinate
      xq += a * a;
      xs += a;
      res += yq;
      res -= 2 * ys * b;
      res += i * (long)b * b;

      // Add the effect of this point
      // for all the previous y - points
      yq += b * b;
      ys += b;
    }

    // Print the desired answer
    System.out.println(res);
  }

  // Driver Code
  public static void main(String[] args)
  {
    int arr[][] = { { 1, 1 },
                   { -1, -1 },
                   { 1, -1 },
                   { -1, 1 } };
    int N = arr.length;
    findSquareSum(arr, N);
  }
}

// This code is contributed by code_hunt.
```

### Python

```python
# Python3 program for the above approach

# Function to find the sum of squares
# of distance between all distinct pairs
def findSquareSum(Coordinates, N):
    xq , yq = 0, 0
    xs , ys = 0, 0

    # Stores final answer
    res = 0

    # Traverse the array
    for i in range(N):

        a = Coordinates[i][0]
        b = Coordinates[i][1]

        res += xq
        res -= 2 * xs * a

        # Adding the effect of this
        # point for all the previous
        # x - points
        res += i * (a * a)

        # Temporarily add the
        # square of x-coordinate
        xq += a * a
        xs += a
        res += yq
        res -= 2 * ys * b
        res += i * b * b

        # Add the effect of this point
        # for all the previous y - points
        yq += b * b
        ys += b

    # Print the desired answer
    print (res)

# Driver Code
if __name__ == '__main__':
    arr = [ [ 1, 1 ],
          [ -1, -1 ],
          [ 1, -1 ],
          [ -1, 1 ] ]

    N = len(arr)

    findSquareSum(arr, N)

# This code is contributed by mohit kumar 29.
```

### C\#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the sum of squares
// of distance between all distinct pairs
static void findSquareSum(int[,] Coordinates, int N)
{
    long xq = 0, yq = 0;
    long xs = 0, ys = 0;

    // Stores final answer
    long res = 0;

    // Traverse the array
    for(int i = 0; i < N ; i++)
    {
        int a, b;

        a = Coordinates[i, 0];
        b = Coordinates[i, 1];

        res += xq;
        res -= 2 * xs * a;

        // Adding the effect of this
        // point for all the previous

        // x - points
        res += i * (long)(a * a);

        // Temporarily add the
        // square of x-coordinate
        xq += a * a;
        xs += a;
        res += yq;
        res -= 2 * ys * b;
        res += i * (long)b * b;

        // Add the effect of this point
        // for all the previous y - points
        yq += b * b;
        ys += b;
    }

    // Print the desired answer
    Console.Write(res);
}

// Driver code
static void Main()
{
    int[,] arr = { { 1, 1 },
                   { -1, -1 },
                   { 1, -1 },
                   { -1, 1 } };
    int N = arr.GetLength(0);

    findSquareSum(arr, N);
}
}

// This code is contributed by code_hunt
```

## java 描述语言

```javascript
<script>

// Javascript program for the above approach

  // Function to find the sum of squares
  // of distance between all distinct pairs
  function findSquareSum(
    Coordinates, N)
  {
    let xq = 0, yq = 0;
    let xs = 0, ys = 0;

    // Stores final answer
    let res = 0;

    // Traverse the array
    for (let i = 0; i < N; i++) {
      let a, b;

      a = Coordinates[i][0];
      b = Coordinates[i][1];

      res += xq;
      res -= 2 * xs * a;

      // Adding the effect of this
      // point for all the previous
      // x - points
      res += i * (a * a);

      // Temporarily add the
      // square of x-coordinate
      xq += a * a;
      xs += a;
      res += yq;
      res -= 2 * ys * b;
      res += i * b * b;

      // Add the effect of this point
      // for all the previous y - points
      yq += b * b;
      ys += b;
    }

    // Print the desired answer
    document.write(res);
  }

// Driver code

    let arr = [[ 1, 1 ],
               [ -1, -1 ],
               [ 1, -1 ],
               [ -1, 1 ]];
    let N = arr.length;
    findSquareSum(arr, N);

</script>
```

`Output:`

```
```

`时间复杂度:` `O(N)`
`辅助空间:` `O(1)`