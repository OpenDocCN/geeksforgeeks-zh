# 3D 矩阵主对角线元素的异或运算

> 原文: [https://www.geeksforgeeks.org/xor-of-major-diagonal-elements-of-a-3d-matrix/](https://www.geeksforgeeks.org/xor-of-major-diagonal-elements-of-a-3d-matrix/)

给定一个由正整数组成的维度为 `N * N * N` 的[三维矩阵](https://www.geeksforgeeks.org/multidimensional-arrays-c-cpp/) `mat[][][]`，任务是计算主对角线上所有矩阵元素的[位异或](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)。

## 示例

> **输入:** `arr[][][]= { {1，2}，{3，4}}，{{5，6}，{7，8 } }`
> **输出:** 12
> **说明:** 主要对角元素为 `{ 1，8，2，7}`。因此，所有这些元素的按位异或是 12。
>
> **输入:** `arr[][][]={{{1}}}`
> **输出:** 0
> **说明:** 矩阵的 2 条主对角线分别为 `{1}`、`{1}`。因此，主对角线元素的按位异或为 0。

## 朴素法

解决问题最简单的方法就是[使用三个](https://www.geeksforgeeks.org/traverse-a-given-matrix-using-recursion/)[嵌套循环](https://www.geeksforgeeks.org/nested-loops-in-c-with-examples-2/)遍历给定的 3D 矩阵 `mat[][][]`，使用变量，比如 `i`、`j` 和 `k`，计算 `mat[i][j][k]` 和 `mat[i][j][N–k–1]` 的按位异或。完成矩阵遍历后，打印得到的按位异或的值。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
void findXOR(
    vector<vector<vector<int> > >& mat,
    int N)
{
    // Stores the Bitwise XOR of
    // the major diagonal elements
    int XOR = 0;

    for (int i = 0; i < N; i++) {

        for (int j = 0; j < N; j++) {

            for (int k = 0; k < N; k++) {

                // If element is part
                // of major diagonal
                if ((i == j && j == k)) {

                    XOR ^= mat[i][j][k];
                    XOR ^= mat[i][j][N - k - 1];
                }
            }
        }
    }

    // Print the resultant Bitwise XOR
    cout << XOR << "\n";
}

// Driver Code
int main()
{
    vector<vector<vector<int> > > mat
        = { { { 1, 2 }, { 3, 4 } },
            { { 5, 6 }, { 7, 8 } } };
    int N = mat.size();

    findXOR(mat, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
static void findXOR(int mat[][][], int N)
{

    // Stores the Bitwise XOR of
    // the major diagonal elements
    int XOR = 0;

    for(int i = 0; i < N; i++)
    {
        for(int j = 0; j < N; j++)
        {
            for(int k = 0; k < N; k++)
            {

                // If element is part
                // of major diagonal
                if ((i == j && j == k))
                {
                    XOR ^= mat[i][j][k];
                    XOR ^= mat[i][j][N - k - 1];
                }
            }
        }
    }

    // Print the resultant Bitwise XOR
    System.out.println(XOR);
}

// Driver Code
public static void main(String[] args)
{
    int mat[][][] = { { { 1, 2 }, { 3, 4 } },
                      { { 5, 6 }, { 7, 8 } } };
    int N = mat.length;

    findXOR(mat, N);
}
}

// This code is contributed by Kingash
```

### Python 3

```python
# Python3 program for the above approach

# Function to calculate Bitwise XOR of
# major diagonal elements of 3D matrix
def findXOR(mat, N):

    # Stores the Bitwise XOR of
    # the major diagonal elements
    XOR = 0

    for i in range(N):
        for j in range(N):
            for k in range(N):

                # If element is part
                # of major diagonal
                if ((i == j and j == k)):
                    XOR ^= mat[i][j][k]
                    XOR ^= mat[i][j][N - k - 1]

    # Print the resultant Bitwise XOR
    print(XOR)

# Driver Code
mat = [ [ [ 1, 2 ], [ 3, 4 ] ],
        [ [ 5, 6 ], [ 7, 8 ] ] ]

N = len(mat)

findXOR(mat, N)

# This code is contributed by splevel62
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
static void findXOR(int[, , ] mat, int N)
{

    // Stores the Bitwise XOR of
    // the major diagonal elements
    int XOR = 0;

    for(int i = 0; i < N; i++)
    {
        for(int j = 0; j < N; j++)
        {
            for(int k = 0; k < N; k++)
            {

                // If element is part
                // of major diagonal
                if ((i == j && j == k))
                {
                    XOR ^= mat[i, j, k];
                    XOR ^= mat[i, j, N - k - 1];
                }
            }
        }
    }

    // Print the resultant Bitwise XOR
    Console.WriteLine(XOR);
}

// Driver Code
public static void Main(string[] args)
{
    int[,,] mat = { { { 1, 2 }, { 3, 4 } },
                    { { 5, 6 }, { 7, 8 } } };
    int N = mat.GetLength(0);

    findXOR(mat, N);
}
}

// This code is contributed by ukasp
```

### JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
function findXOR(mat, N)
{

    // Stores the Bitwise XOR of
    // the major diagonal elements
    let XOR = 0;

    for(let i = 0; i < N; i++)
    {
        for(let j = 0; j < N; j++)
        {
            for(let k = 0; k < N; k++)
            {

                // If element is part
                // of major diagonal
                if ((i == j && j == k))
                {
                    XOR ^= mat[i][j][k];
                    XOR ^= mat[i][j][N - k - 1];
                }
            }
        }
    }

    // Print the resultant Bitwise XOR
    document.write(XOR);
}

// Driver Code

    let mat = [[[1, 2 ], [ 3, 4 ]],
                     [[ 5, 6 ], [ 7, 8 ]]];
    let N = mat.length;

    findXOR(mat, N);

</script>
```

**输出:**

**时间复杂度:** `O(N^3)`
**辅助空间:** `O(1)`

## 高效方法

上述方法可以通过使用其指数 `i`、`j` 和 `k` 与对角元素相同的元素来优化。因此，其思想是使用变量 `i` 迭代索引 `[0，N–1]` 的范围，并在给定矩阵 `mat[][][]` 中的索引 `(i，i，i)` 和 `(i，i，N–i–1)` 处计算作为主对角线一部分的所有元素的位异或。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the Bitwise XOR of
// both diagonal elements of 3D matrix
void findXOR(
    vector<vector<vector<int> > >& mat,
    int N)
{
    // Stores the Bitwise XOR of the
    // major diagonal elements
    int XOR = 0;

    for (int i = 0; i < N; i++) {

        XOR ^= mat[i][i][i];
        XOR ^= mat[i][i][N - i - 1];
    }

    // Print the resultant Bitwise XOR
    cout << XOR << "\n";
}

// Driver Code
int main()
{
    vector<vector<vector<int> > > mat
        = { { { 1, 2 }, { 3, 4 } },
            { { 5, 6 }, { 7, 8 } } };
    int N = mat.size();

    findXOR(mat, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
static void findXOR(int mat[][][], int N)
{

    // Stores the Bitwise XOR of the
    // major diagonal elements
    int XOR = 0;

    for(int i = 0; i < N; i++)
    {
        XOR ^= mat[i][i][i];
        XOR ^= mat[i][i][N - i - 1];
    }

    // Print the resultant Bitwise XOR
    System.out.println(XOR);
}

// Driver Code
public static void main(String[] args)
{
    int mat[][][] = { { { 1, 2 }, { 3, 4 } },
                      { { 5, 6 }, { 7, 8 } } };
    int N = mat.length;

    findXOR(mat, N);
}
}

// This code is contributed by Kingash
```

### Python 3

```python
# Python3 program for the above approach

# Function to find the Bitwise XOR of
# both diagonal elements of 3D matrix
def findXOR(mat, N):

    # Stores the Bitwise XOR of the
    # major diagonal elements
    XOR = 0

    for i in range(N):
        XOR ^= mat[i][i][i]
        XOR ^= mat[i][i][N - i - 1]

    # Print the resultant Bitwise XOR
    print(XOR)

# Driver Code
mat = [ [ [ 1, 2 ], [ 3, 4 ] ],
        [ [ 5, 6 ], [ 7, 8 ] ] ]
N = len(mat)

findXOR(mat, N)

# This code is contributed by sanjoy_62
```

## C#

```
// C# program for the above approach
using System;

class GFG{

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
static void findXOR(int[,,] mat, int N)
{

    // Stores the Bitwise XOR of the
    // major diagonal elements
    int XOR = 0;

    for(int i = 0; i < N; i++)
    {
        XOR ^= mat[i, i, i];
        XOR ^= mat[i, i, N - i - 1];
    }

    // Print the resultant Bitwise XOR
    Console.Write(XOR);
}

// Driver Code
static public void Main ()
{
    int[,,] mat = { { { 1, 2 }, { 3, 4 } },
                    { { 5, 6 }, { 7, 8 } } };
    int N = mat.GetLength(0);

    findXOR(mat, N);
}
}

// This code is contributed by avijitmondal1998
```

## JavaScript

```
<script>

// Javascript program for the above approach

// Function to calculate Bitwise XOR of
// major diagonal elements of 3D matrix
function findXOR( mat,  N)
{

    // Stores the Bitwise XOR of the
    // major diagonal elements
    let XOR = 0;

    for(let i = 0; i < N; i++)
    {
        XOR ^= mat[i][i][i];
        XOR ^= mat[i][i][N - i - 1];
    }

    // Print the resultant Bitwise XOR
    document.write(XOR);
}

// Driver Code

let mat = [ [ [ 1, 2 ], [ 3, 4 ] ],
          [ [ 5, 6 ], [ 7, 8 ] ] ];
let N = mat.length;

findXOR(mat, N);;

</script>
```

`Output:`

```

```

时间复杂度: O(N)
辅助空间: O(1)