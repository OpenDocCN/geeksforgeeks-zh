# 检查每个子序列的乘积是否为完美平方

> 原文: [https://www.geeksforgeeks.org/check-whether-the-product-of-every-subsequence-is-a-perfect-square-or-not/](https://www.geeksforgeeks.org/check-whether-the-product-of-every-subsequence-is-a-perfect-square-or-not/)

给定一个由 `N` 个正整数组成的数组 `arr[]`，任务是检查给定数组 `arr[]` 的每个子序列的元素乘积是否为完美平方。如果发现为真，则打印 `是`。否则，打印 `否`。

## 示例

> **输入:** `arr[] = {1，4，100}`
> **输出:** `是`
> **解释:**
> 以下是给定数组 `arr[]` 的子序列:
> 1.  `{1}`，乘积等于 `1`，是一个完美的正方形。
> 2.  `{1，4}`，乘积等于 `4`，是一个完美的正方形。
> 3.  `{1，100}`，乘积等于 `100`，是一个完美的正方形。
> 4.  `{1，4，100}`，乘积等于 `400`，是一个完美的正方形。
> 5.  `{4}`，乘积等于 `4`，是一个完美的正方形。
> 6.  `{4，100}`，乘积等于 `400`，是一个完美的正方形。
> 7.  `{100}`，乘积等于 `100`，是一个完美的正方形。
>
> 因此，打印 `是`。

> **输入:** `arr[] = {1，3}`
> **输出:** `否`

## 天真方法

解决给定问题最简单的方法是生成给定数组的所有可能的子序列，如果每个子序列的乘积元素是一个完美的正方形，那么打印 `是`。否则，打印 `否`。

**时间复杂度:** `O(N * 2^N)`
**辅助空间:** `O(1)`

## 高效方法

利用两个完美平方数的乘积也将是一个完美平方的事实，也可以优化上述方法。因此，要检查所有子序列元素的单个乘积是否是完美平方，思路是检查所有数组元素是否是完美平方。如果发现为真，则打印 `是`。否则，打印 `否`。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if the product of
// every subsequence of the array is a
// perfect square or not
string perfectSquare(int arr[], int N)
{
    // Traverse the given array
    for (int i = 0; i < N; i++) {

        // If arr[i] is a perfect
        // square or not
        int p = sqrt(arr[i]);

        if (p * p != arr[i]) {
            return "No";
        }
    }

    // Return "Yes"
    return "Yes";
}

// Driver Code
int main()
{
    int arr[] = { 1, 4, 100 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << perfectSquare(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;

class GFG{

// Function to check if the product of
// every subsequence of the array is a
// perfect square or not
static String perfectSquare(int arr[], int N)
{

    // Traverse the given array
    for(int i = 0; i < N; i++)
    {

        // If arr[i] is a perfect
        // square or not
        int p = (int)Math.sqrt(arr[i]);

        if (p * p != arr[i])
        {
            return "No";
        }
    }

    // Return "Yes"
    return "Yes";
}

// Driver Code
public static void main (String[] args)
{
    int arr[] = { 1, 4, 100 };
    int N = arr.length;

    System.out.println(perfectSquare(arr, N));
}
}

// This code is contributed by Potta Lokesh
```

## Python 3

```python
# Python 3 program for the above approach
from math import sqrt

# Function to check if the product of
# every subsequence of the array is a
# perfect square or not
def perfectSquare(arr, N):

    # Traverse the given array
    for i in range(N):

        # If arr[i] is a perfect
        # square or not
        p = sqrt(arr[i])

        if (p * p != arr[i]):
            return "No"

    # Return "Yes"
    return "Yes"

# Driver Code
if __name__ == '__main__':
    arr = [1, 4, 100]
    N = len(arr)
    print(perfectSquare(arr, N))

    # This code is contributed by ipg2016107.
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if the product of
// every subsequence of the array is a
// perfect square or not
static String perfectSquare(int[] arr, int N)
{

    // Traverse the given array
    for(int i = 0; i < N; i++)
    {

        // If arr[i] is a perfect
        // square or not
        int p = (int)Math.Sqrt(arr[i]);

        if (p * p != arr[i])
        {
            return "No";
        }
    }

    // Return "Yes"
    return "Yes";
}

// Driver Code
public static void Main()
{
    int[] arr = { 1, 4, 100 };
    int N = arr.Length;

    Console.WriteLine(perfectSquare(arr, N));
}
}

// This code is contributed by subham348
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to check if the product of
// every subsequence of the array is a
// perfect square or not
function perfectSquare(arr, N)
{

    // Traverse the given array
    for(let i = 0; i < N; i++)
    {

        // If arr[i] is a perfect
        // square or not
        let p = Math.sqrt(arr[i]);

        if (p * p != arr[i])
        {
            return "No";
        }
    }

    // Return "Yes"
    return "Yes";
}

// Driver Code
let arr = [ 1, 4, 100 ];
let N = arr.length;

document.write(perfectSquare(arr, N));

// This code is contributed by target_2
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`