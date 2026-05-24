# 从给定数组生成的矩阵的子矩阵的逐位异或

> 原文：[https://www.geeksforgeeks.org/bitwise-xor-of-a-submatrix-of-a-matrix-generated-from-a-given-array/](https://www.geeksforgeeks.org/bitwise-xor-of-a-submatrix-of-a-matrix-generated-from-a-given-array/)

给定一个长度为 `N` 的数组 `arr[]`，在数组 `arr[]` 上定义了一个尺寸矩阵 `N * N`，其中 `M[i][j] = arr[i] & arr[j]`。给定四个整数 `X`，`Y`，`S` 和 `T`，任务是从左上角 `(X, Y)` 到右下角 `(S, T)` 找到子矩阵所有元素的按位异或。

**示例：**

> **输入：** `N = 3`，`A[] = {2, 3, 4}`，`(X, Y) = (0, 1)`，`(S, T) = (2, 2)`
> **输出：** `5`
> **说明：**
> `A` 上定义的矩阵为
> `{(2&2), (2 & 3), (2 & 4)}`，
> `{(3 & 2), (3 & 3), (3 & 4)}`，
> `{(4 & 2), (4 & 3), (4 & 4)}`
> 最后，矩阵将为：
> `{{2, 2, 0}, {2, 3, 0}, {0, 0, 4}}`
> **XOR 值** = `(2^2)^(2^3)^(0^0)^(2^0)^(3^0)^(0^4) = 5`
>
> **输入：** `N=3`，`A[]={1, 2, 3}`，`(X, Y)=(0, 1)`，`(S, T)=(1, 2)`
> **输出：** `1`

**朴素方法：** 最简单的方法是从给定的数组中生成矩阵 `M`，并计算 `M` 的给定子矩阵中存在的所有元素的按位异或。

*   **时间复杂度：** `O(N^2)`
*   **辅助空间：** `O(N^2)`

**有效方法：** 想法是使用“异或”和“与”运算的以下分配属性：

> `(a ^ b) & c = (a & c) ^ (b & c)`

因此，从左上方 `(X, Y)` 到右下方 `(S, T)` 的子矩阵的最终异或可以由以下等式计算：

> **最终异或**
> = `(M[X][Y] ^ M[X][Y+1] ^ ... ^ M[X][T]) ^ ... ^ (M[S][Y] ^ M[S][Y+1] ^ ... ^ M[S][T])`
> = `(A[X] & A[Y]) ^ (A[X] & A[Y+1]) ^ ... ^ (A[X] & A[T]) ^ ... ^ (A[S] & A[Y]) ^ (A[S] & A[Y+1]) ^ ... ^ (A[S] & A[T])`
> = `(A[Y] ^ A[Y+1] ^ ... ^ A[T]) & (A[X] ^ A[X+1] ^ ... ^ A[S])`

*   迭代数组从索引 `Y` 到 `T` 并计算元素的异或。
*   遍历数组从索引 `X` 到 `S` 并计算元素的异或。
*   最后，计算计算出的异或的按位“与”，它等于子矩阵从 `(X, Y)` 到 `(S, T)` 的按位“异或”。

下面是上述方法的实现：

## C++

```cpp
// C++ program of the above approach
#include <iostream>
using namespace std;

// Function to find the submatrix XOR of the given matrix
int submatrix_xor(int* A, int N, int X, int Y, int S, int T)
{
    int left_xor = 0, i, right_xor = 0;

    // Calculating left xor i.e A[Y]^A[Y+1]^. . .^A[T]
    for (i = Y; i <= T; i++) {
        left_xor ^= A[i];
    }

    // Calculating right xor i.e A[X]^A[X+1]^. . .^A[S]
    for (i = X; i <= S; i++) {
        right_xor ^= A[i];
    }

    // Bitwise AND of left_xor and right_xor gives required result
    return left_xor & right_xor;
}

// Driver Code
int main()
{
    int A[3] = { 2, 3, 4 }, X = 0, Y = 1, S = 2, T = 2, N = 3;

    // Printing xor of submatrix
    cout << submatrix_xor(A, N, X, Y, S, T);
    return 0;
}
```

## Java

```java
// Java program of the above approach
import java.io.*;

class GFG{

// Function to find the submatrix XOR of the given matrix
static int submatrix_xor(int[] A, int N, int X, int Y, int S, int T)
{
    int left_xor = 0, i, right_xor = 0;

    // Calculating left xor i.e A[Y]^A[Y+1]^. . .^A[T]
    for(i = Y; i <= T; i++)
    {
        left_xor ^= A[i];
    }

    // Calculating right xor i.e A[X]^A[X+1]^. . .^A[S]
    for(i = X; i <= S; i++)
    {
        right_xor ^= A[i];
    }

    // Bitwise AND of left_xor and right_xor gives required result
    return left_xor & right_xor;
}

// Driver Code
public static void main (String[] args)
{
    int[] A = { 2, 3, 4 };
    int X = 0, Y = 1, S = 2, T = 2, N = 3;

    // Printing xor of submatrix
    System.out.print(submatrix_xor(A, N, X, Y, S, T));
}
}

// This code is contributed by code_hunt
```

## Python 3

```python
# Python3 program of the above approach

# Function to find the submatrix XOR of the given matrix
def submatrix_xor(A, N, X, Y, S, T):

    left_xor = 0
    i = 0
    right_xor = 0

    # Calculating left xor i.e A[Y]^A[Y+1]^. . .^A[T]
    for i in range(Y, T + 1):
        left_xor ^= A[i]

    # Calculating right xor i.e A[X]^A[X+1]^. . .^A[S]
    for i in range(X, S + 1):
        right_xor ^= A[i]

    # Bitwise AND of left_xor and right_xor gives required result
    return left_xor & right_xor

# Driver Code
if __name__ == '__main__':

    A = [ 2, 3, 4 ]
    X = 0
    Y = 1
    S = 2
    T = 2
    N = 3

    # Printing xor of submatrix
    print(submatrix_xor(A, N, X, Y, S, T))

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the submatrix XOR of the given matrix
static int submatrix_xor(int[] A, int N, int X, int Y, int S, int T)
{
    int left_xor = 0, i, right_xor = 0;

    // Calculating left xor i.e A[Y]^A[Y+1]^. . .^A[T]
    for(i = Y; i <= T; i++)
    {
        left_xor ^= A[i];
    }

    // Calculating right xor i.e A[X]^A[X+1]^. . .^A[S]
    for(i = X; i <= S; i++)
    {
        right_xor ^= A[i];
    }

    // Bitwise AND of left_xor and right_xor gives required result
    return left_xor & right_xor;
}

// Driver Code
public static void Main ()
{
    int[] A = { 2, 3, 4 };
    int X = 0, Y = 1, S = 2, T = 2, N = 3;

    // Printing xor of submatrix
    Console.Write(submatrix_xor(A, N, X, Y, S, T));
}
}

// This code is contributed by code_hunt
```

## JavaScript

```javascript
<script>
// JavaScript program to implement the above approach

// Function to find the submatrix XOR of the given matrix
function submatrix_xor(A, N, X, Y, S, T)
{
    let left_xor = 0, i, right_xor = 0;

    // Calculating left xor i.e A[Y]^A[Y+1]^. . .^A[T]
    for(i = Y; i <= T; i++)
    {
        left_xor ^= A[i];
    }

    // Calculating right xor i.e A[X]^A[X+1]^. . .^A[S]
    for(i = X; i <= S; i++)
    {
        right_xor ^= A[i];
    }

    // Bitwise AND of left_xor and right_xor gives required result
    return left_xor & right_xor;
}

// Driver code
let A = [ 2, 3, 4 ];
let X = 0, Y = 1, S = 2, T = 2, N = 3;

// Printing xor of submatrix
document.write(submatrix_xor(A, N, X, Y, S, T));

// This code is contributed by target_2.
</script>
```

**Output:**

```
5
```

*   **时间复杂度：** `O(N)`，其中 `N` 为阵的大小
*   **辅助空间：** `O(1)`