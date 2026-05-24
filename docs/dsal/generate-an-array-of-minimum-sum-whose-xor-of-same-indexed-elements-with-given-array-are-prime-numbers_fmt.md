# 生成一个最小和数组，其给定数组的同索引元素的异或是素数

> 原文: [https://www.geeksforgeeks.org/generate-an-array-of-minimum-sum-whose-xor-of-same-indexed-elements-with-given-array-are-prime-numbers/](https://www.geeksforgeeks.org/generate-an-array-of-minimum-sum-whose-xor-of-same-indexed-elements-with-given-array-are-prime-numbers/)

## 问题描述

给定一个由 `n` (`1≤n≤10^5`) 个整数组成的数组 `arr[]`，任务是生成一个由 `N` 个非零元素组成的数组 `b[]`，使得 `a[i] ^ b[i]` 是一个素数。

**注:** 应尽量减少得到的异或之和。

## 示例

**输入:**
`arr[] = {5, 4, 7, 6}`

**输出:**
`{7, 6, 5, 4}`

**说明:**
`2` 是最小素数。因此，将 `A[i]` 与 `(A[i] ^ 2)` 进行异或运算，给出了最小的素数。
`a[i]^(a[i]^ 2)=(a[i]^ a[i])^ 2 = 0 ^ 2 = 2`
因为：
1.  `5` 的异或 `^ 7 = 2`，即素数。
2.  `4 ^ 6 = 2` 的异或，它是素数。
3.  `7 ^ 5 = 2` 的异或，它是素数。
4.  `6 ^ 4 = 2` 的异或，它是素数。
结果总和为 `2+2+2+2 = 8`，这是最小可能值。

**输入:**
`arr[] = {10, 16}`

**输出:**
`{8, 18}`

## 方法

这个问题可以用贪婪算法解决。按照以下步骤解决问题：

1.  因为 `2` 是可能的最小素数，所以 `Arr[i]` 与 `B[i] = (Arr[i] ^ 2)` 的 `XOR` 将给出一个素数 `2`。
2.  当任何数组元素本身为 `Arr[i] = 2` 时，矛盾就产生了。在这种情况下，`B[i] = 2 ^ 2` 导致 `0`。
3.  因此，如果 `Arr[i] = 2`，设置 `B[i] = (2 ^ 3) = 1`，使得 `Arr[i] ^ K = 3`，下一个最小素数。

## 代码实现

下面是上述方法的实现：

### C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to generate an array whose XOR
// with same-indexed elements of the given
// array is always a prime
void minXOR(vector<int>& Arr, int N)
{
    // Traverse the array
    for (int i = 0; i < N; i++) {

        // If current array element is 2
        if (Arr[i] == 2) {

            // Print its XOR with 3
            cout << (Arr[i] ^ 3) << " ";
        }
        // Otherwise
        else {

            // Print its XOR with 2
            cout << (Arr[i] ^ 2) << " ";
        }
    }
}

// Driver Code
int main()
{
    // Given array
    vector<int> Arr = { 5, 4, 7, 6 };

    // Size of the array
    int N = Arr.size();

    // Prints the required array
    minXOR(Arr, N);
    return 0;
}
```

### Java

```java
// Java implementation of the above approach
class GFG{

// Function to generate an array whose XOR
// with same-indexed elements of the given
// array is always a prime
private static void minXOR(int Arr[], int N)
{

    // Traverse the array
    for(int i = 0; i < N; i++)
    {

        // If current array element is 2
        if (Arr[i] == 2)
        {

            // Print its XOR with 3
            System.out.print((Arr[i] ^ 3) + " ");
        }

        // Otherwise
        else
        {

            // Print its XOR with 2
            System.out.print((Arr[i] ^ 2) + " ");
        }
    }
}

// Driver code
public static void main(String[] args)
{

    // Given array
    int Arr[] = { 5, 4, 7, 6 };

    // Size of the array
    int N = Arr.length;

    // Prints the required array
    minXOR(Arr, N);
}
}
```

### Python

```python
# Python3 implementation of the above approach

# Function to generate an array whose XOR
# with same-indexed elements of the given
# array is always a prime
def minXOR(Arr, N):

    # Traverse the array
    for i in range(N):

        # If current array element is 2
        if (Arr[i] == 2):

            # Print its XOR with 3
            print(Arr[i] ^ 3,end=" ")
        # Otherwise
        else:

            # Print its XOR with 2
            print(Arr[i] ^ 2,end=" ")

# Driver Code
if __name__ == '__main__':

    # Given array
    Arr = [5, 4, 7, 6 ]

    # Size of the array
    N = len(Arr)

    # Prints the required array
    minXOR(Arr, N)
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to generate an array whose XOR
// with same-indexed elements of the given
// array is always a prime
private static void minXOR(int[] Arr, int N)
{

    // Traverse the array
    for(int i = 0; i < N; i++)
    {

        // If current array element is 2
        if (Arr[i] == 2)
        {

            // Print its XOR with 3
            Console.Write((Arr[i] ^ 3) + " ");
        }

        // Otherwise
        else
        {

            // Print its XOR with 2
            Console.Write((Arr[i] ^ 2) + " ");
        }
    }
}

// Driver code
public static void Main()
{

    // Given array
    int[] Arr = { 5, 4, 7, 6 };

    // Size of the array
    int N = Arr.Length;

    // Prints the required array
    minXOR(Arr, N);
}
}
```

### JavaScript

```javascript
// JavaScript implementation of the above approach

// Function to generate an array whose XOR
// with same-indexed elements of the given
// array is always a prime
function minXOR(Arr, N)
{

    // Traverse the array
    for(let i = 0; i < N; i++)
    {

        // If current array element is 2
        if (Arr[i] == 2)
        {

            // Print its XOR with 3
            document.write((Arr[i] ^ 3) + " ");
        }

        // Otherwise
        else
        {

            // Print its XOR with 2
            document.write((Arr[i] ^ 2) + " ");
        }
    }
}

// Driver code

    // Given array
    let Arr = [ 5, 4, 7, 6 ];

    // Size of the array
    let N = Arr.length;

    // Prints the required array
    minXOR(Arr, N);
```

**输出:**

```
7 6 5 4
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`