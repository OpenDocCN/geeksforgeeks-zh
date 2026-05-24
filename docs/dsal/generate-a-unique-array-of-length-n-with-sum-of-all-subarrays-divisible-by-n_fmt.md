# 生成长度为 N 的唯一数组，所有子数组的和可被 N 整除

> 原文：[https://www.geeksforgeeks.org/generate-a-unique-array-of-length-n-with-sum-of-all-subarrays-divisible-by-n/](https://www.geeksforgeeks.org/generate-a-unique-array-of-length-n-with-sum-of-all-subarrays-divisible-by-n/)

给定一个整数 `N`，任务是制作一个长度为 `N` 的唯一元素的数组，使得所有子数组的和模 `N` 等于零。

## 示例

> **输入:** `N = 6`
> **输出:** `6 12 18 24 30 36`
> **解释:**
> 因为所有元素都是 `6` 的倍数。因此所有子阵列加起来就是一个可被 `6` 整除的和。
> **输入:** `N = 4`
> **输出:** `4 8 12 16`

## 方法

我们可以观察到，要让所有子阵列都能被 `N` 整除，阵列的元素需要是 `N` 的倍数。

## 图解

> 对于 `N = 4`，如果我们考虑数组元素为 `{4, 8, 12, 16}`，所有可能的子数组为:
> `{4}`、`{8}`、`{12}`、`{16}`、`{4, 8}`、`{8, 12}`、`{12, 16}`、`{4, 8, 12}`、`{4, 8, 12, 16}`、`{8, 12, 16}`、`{4, 12, 16}`
> 因此，所有子数组的和可被 `N` 除尽。

因此，要解决这个问题，我们只需要打印 `{N, 2*N, 3*N, ….., N*N}` 得到想要的数组。

以下是上述办法的实施情况：

## C++

```cpp
// C++ implementation of the
// above approach

#include <bits/stdc++.h>
using namespace std;

// Function to print the required
// array
void makeArray(int a[], int n)
{
    // Print the array
    for (int i = 1; i <= n; i++)
        cout << i * n << " ";
}

// Driver Program
int main()
{
    int N = 6;
    int arr[N];
    makeArray(arr, N);
}
```

## Java

```java
// Java program for the above approach
class GFG{

// Function to print the required
// array
static void makeArray(int a[], int n)
{

    // Print the array
    for(int i = 1; i <= n; i++)
       System.out.print(i * n + " ");
}

// Driver code
public static void main(String[] args)
{
    int N = 6;
    int arr[] = new int[N];

    makeArray(arr, N);
}
}

// This code is contributed by Pratima Pandey
```

## Python 3

```python
# Python3 implementation of the
# above approach

# Function to print the
# required array
def makeArray(n):

    # Print Array
    for i in range(n):
        print((i + 1) * n, end =" ")

# Driver code
n = 6;
makeArray(n);
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG{

// Function to print the required
// array
static void makeArray(int []a, int n)
{

    // Print the array
    for(int i = 1; i <= n; i++)
    Console.Write(i * n + " ");
}

// Driver code
public static void Main()
{
    int N = 6;
    int []arr = new int[N];

    makeArray(arr, N);
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
// javascript program for the above approach

// Function to print the required
// array
function makeArray(n)
{

    // Print the array
    for(var i = 1; i <= n; i++)
    document.write(i * n + " ");
}

// Driver code
var N = 6;
makeArray(N);
```

**输出:**

```
6 12 18 24 30 36
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`