# 计算替换数组元素的不同方式，使得数组的乘积变成偶数

原文: [https://www.geeksforgeeks.org/count-distinct-ways-to-replace-array-elements-such-that-product-of-the-array-becomes-even/](https://www.geeksforgeeks.org/count-distinct-ways-to-replace-array-elements-such-that-product-of-the-array-becomes-even/)

给定一个由奇数 `N` 组成的数组 `arr[]`，任务是通过将任意一组元素重复更改为任意值，计算出使所有数组元素的乘积为偶数的不同方法。由于计数会很大，打印到模 `10^9 + 7`。

## 示例

**输入:** `arr[] = {1，3}`
**输出:** `3`
**说明:** 数组元素乘积为奇数的所有可能方法如下:
- 用任意偶数替换 `arr[0]`。数组 `arr[]` 修改为 `{偶数，3}`。因此，数组的乘积 = 偶数 * 3 = 偶数。
- 用任意偶数替换 `arr[1]`。数组 `arr[]` 修改为 `{1，偶数}`。因此，数组的乘积 = 1 * 偶数 = 偶数。
- 用偶数替换 `arr[0]` 和 `arr[1]`。因为两个数组元素都变成偶数，所以数组的乘积变成偶数。因此，使数组均匀的不同方法的总数是 3。

**输入:** `arr[] = {1，2，3，4，5}`
**输出:** `31`

## 方法

解决给定问题的思路是基于这样的观察: 只有当数组中至少存在一个偶元素时，数组的积才是偶的。因此，不同路的总数可以通过给定阵列的不同子集的数量来计算。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
#define M 1000000007
using namespace std;

// Function to find the value of (x^y)
long long power(long long x, long long y,
                long long p)
{
    // Stores the result
    long long res = 1;

    while (y > 0) {

        // If y is odd, then
        // multiply x with res
        if (y & 1)
            res = (res * x) % p;

        // y must be even now
        y = y >> 1;

        // Update x
        x = (x * x) % p;
    }
    return res;
}

// Function to count the number of ways
// to make the product of an array even
// by replacing array elements
int totalOperations(int arr[], int N)
{
    // Find the value ( 2 ^ N ) % M
    long long res = power(2, N, M);

    // Exclude empty subset
    res--;

    // Print the answer
    cout << res;
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    totalOperations(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG{

static long M = 1000000007;

// Function to find the value of (x^y)
static long power(long x, long y, long p)
{

    // Stores the result
    long res = 1;

    while (y > 0)
    {

        // If y is odd, then
        // multiply x with res
        if ((y & 1) > 0)
            res = (res * x) % p;

        // y must be even now
        y = y >> 1;

        // Update x
        x = (x * x) % p;
    }
    return res;
}

// Function to count the number of ways
// to make the product of an array even
// by replacing array elements
static int totalOperations(int arr[], int N)
{

    // Find the value ( 2 ^ N ) % M
    long res = power(2, N, M);

    // Exclude empty subset
    res--;

    // Print the answer
    System.out.print(res);
    return 0;
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = arr.length;

    totalOperations(arr, N);
}
}

// This code is contributed by rag2127
```

### Python 3

```python
# Python3 program for the above approach
M = 1000000007

# Function to find the value of (x^y)
def power(x, y, p):

    global M

    # Stores the result
    res = 1

    while (y > 0):

        # If y is odd, then
        # multiply x with res
        if (y & 1):
            res = (res * x) % p;

        # y must be even now
        y = y >> 1

        # Update x
        x = (x * x) % p

    return res

# Function to count the number of ways
# to make the product of an array even
# by replacing array elements
def totalOperations(arr, N):

    # Find the value ( 2 ^ N ) % M
    res = power(2, N, M)

    # Exclude empty subset
    res-=1

    # Print the answer
    print (res)

# Driver Code
if __name__ == '__main__':

    arr = [1, 2, 3, 4, 5]
    N = len(arr)

    totalOperations(arr, N)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG {

static long M = 1000000007;

// Function to find the value of (x^y)
static long power(long x, long y, long p)
{

    // Stores the result
    long res = 1;

    while (y > 0)
    {

        // If y is odd, then
        // multiply x with res
        if ((y & 1) > 0)
            res = (res * x) % p;

        // y must be even now
        y = y >> 1;

        // Update x
        x = (x * x) % p;
    }
    return res;
}

// Function to count the number of ways
// to make the product of an array even
// by replacing array elements
static int totalOperations(int[] arr, int N)
{

    // Find the value ( 2 ^ N ) % M
    long res = power(2, N, M);

    // Exclude empty subset
    res--;

    // Print the answer
    Console.Write(res);
    return 0;
}

// Calculating gcd
static int gcd(int a, int b)
{
    if (b == 0)
        return a;

    return gcd(b, a % b);
}

// Driver code
static void Main()
{
    int[] arr = { 1, 2, 3, 4, 5 };
    int N = arr.Length;

    totalOperations(arr, N);
}
}

// This code is contributed by sanjoy_62.
```

### JavaScript

```javascript
<script>

    let M = 1000000007;
    // Function to find the value of (x^y)
    function power(x,y,p)
    {
        // Stores the result
        let res = 1;
        while (y > 0)
        {

            // If y is odd, then
            // multiply x with res
            if ((y & 1) > 0)
                res = (res * x) % p;

            // y must be even now
            y = y >> 1;

            // Update x
            x = (x * x) % p;
        }
        return res;
    }

    // Function to count the number of ways
    // to make the product of an array even
    // by replacing array elements
    function totalOperations(arr,N)
    {
        // Find the value ( 2 ^ N ) % M
        let res = power(2, N, M);
        // Exclude empty subset
        res--;
        // Print the answer
        document.write(res);
    }

    // Driver Code
    let arr=[ 1, 2, 3, 4, 5];
    let N = arr.length;
    totalOperations(arr, N);

    // This code is contributed by avanitrachhadiya2155

</script>
```

**输出:**

```
31
```

**时间复杂度:** `O(log N)`
**辅助空间:** `O(1)`