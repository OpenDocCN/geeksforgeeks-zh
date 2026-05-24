# 数组中元素的二进制表示中出现的集合位的计数乘积

> 原文：[https://www.geeksforgeeks.org/product-of-count-of-set-bits-present-in-binary-representations-of-elements-in-an-array/](https://www.geeksforgeeks.org/product-of-count-of-set-bits-present-in-binary-representations-of-elements-in-an-array/)

给定一个由 `N` 个整数组成的数组 `arr[]`，任务是在每个数组元素的二进制表示中找到设置位的计数的乘积。

**示例：**

> **输入：** `arr[] = {3, 2, 4, 1, 5}`
> **输出：** `4`
> **解释：**
> 数组元素的二进制表示分别为 `{3, 2, 4, 1, 5}` 为 `{"11", "10", "100", "1", "101"}`。
> 因此，集合比特数的乘积 = `(2 * 1 * 1 * 1 * 2) = 4`。

> **输入：** `arr[] = {10, 11, 12}`
> **输出：** `12`

**方法：** 给定的问题可以通过计算每个数组元素的二进制表示中的总位数来解决。按照以下步骤解决问题：

*   初始化一个变量，比如 `product`，来存储结果产品。
*   遍历给定数组 `arr[]`，并执行以下步骤：
    *   计算一个整数的设定位数 `arr[i]` 并将其存储在一个变量中，比如 `bits`。
    *   将 `product` 的值更新为 `product * bits`。
*   完成上述步骤后，打印 `product` 的值作为结果。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to count the
// set bits in an integer
int countbits(int n)
{
    // Stores the count of set bits
    int count = 0;

    // Iterate while N is not equal to 0
    while (n != 0) {

        // Increment count by 1
        if (n & 1)
            count++;

        // Divide N by 2
        n = n / 2;
    }

    // Return the total count obtained
    return count;
}

// Function to find the product
// of count of set bits present
// in each element of an array
int BitProduct(int arr[], int N)
{
    // Stores the resultant product
    int product = 1;

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // Stores the count
        // of set bits of arr[i]
        int bits = countbits(arr[i]);

        // Update the product
        product *= bits;
    }

    // Return the resultant product
    return product;
}

// Driver Code
int main()
{
    int arr[] = { 3, 2, 4, 1, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << BitProduct(arr, N);

    return 0;
}
```

## Java

```java
// java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

public class GFG {

    // Function to count the
    // set bits in an integer
    static int countbits(int n)
    {
        // Stores the count of set bits
        int count = 0;

        // Iterate while N is not equal to 0
        while (n != 0) {

            // Increment count by 1
            if ((n & 1) != 0)
                count++;

            // Divide N by 2
            n = n / 2;
        }

        // Return the total count obtained
        return count;
    }

    // Function to find the product
    // of count of set bits present
    // in each element of an array
    static int BitProduct(int arr[], int N)
    {

        // Stores the resultant product
        int product = 1;

        // Traverse the array arr[]
        for (int i = 0; i < N; i++) {

            // Stores the count
            // of set bits of arr[i]
            int bits = countbits(arr[i]);

            // Update the product
            product *= bits;
        }

        // Return the resultant product
        return product;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 3, 2, 4, 1, 5 };
        int N = arr.length;
        System.out.print(BitProduct(arr, N));
    }
}

// This code is contributed by Kingash.
```

## Python 3

```python
# Python3 program for the above approach

# Function to count the
# set bits in an integer
def countbits(n):

    # Stores the count of set bits
    count = 0

    # Iterate while N is not equal to 0
    while (n != 0):

        # Increment count by 1
        if (n & 1):
            count += 1

        # Divide N by 2
        n = n // 2

    # Return the total count obtained
    return count

# Function to find the product
# of count of set bits present
# in each element of an array
def BitProduct(arr, N):

    # Stores the resultant product
    product = 1

    # Traverse the array arr[]
    for i in range(N):

        # Stores the count
        # of set bits of arr[i]
        bits = countbits(arr[i])

        # Update the product
        product *= bits

    # Return the resultant product
    return product

# Driver Code
if __name__ == '__main__':
    arr = [3, 2, 4, 1, 5]
    N = len(arr)
    print(BitProduct(arr, N))

    # This code is contributed by mohit kumar 29.
```

## C#

```csharp
// C# program for the above approach
using System;

public class GFG {

    // Function to count the
    // set bits in an integer
    static int countbits(int n)
    {
        // Stores the count of set bits
        int count = 0;

        // Iterate while N is not equal to 0
        while (n != 0) {

            // Increment count by 1
            if ((n & 1) != 0)
                count++;

            // Divide N by 2
            n = n / 2;
        }

        // Return the total count obtained
        return count;
    }

    // Function to find the product
    // of count of set bits present
    // in each element of an array
    static int BitProduct(int[] arr, int N)
    {

        // Stores the resultant product
        int product = 1;

        // Traverse the array arr[]
        for (int i = 0; i < N; i++) {

            // Stores the count
            // of set bits of arr[i]
            int bits = countbits(arr[i]);

            // Update the product
            product *= bits;
        }

        // Return the resultant product
        return product;
    }

    // Driver Code
    public static void Main(string[] args)
    {
        int[] arr = { 3, 2, 4, 1, 5 };
        int N = arr.Length;
        Console.Write(BitProduct(arr, N));
    }
}

// This code is contributed by ukasp.
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to count the
// set bits in an integer
function countbits( n)
{
    // Stores the count of set bits
    let count = 0;

    // Iterate while N is not equal to 0
    while (n != 0) {

        // Increment count by 1
        if ((n & 1) != 0)
            count++;

        // Divide N by 2
        n = Math.floor(n / 2);
        }

    // Return the total count obtained
    return count;
}

// Function to find the product
// of count of set bits present
// in each element of an array
function BitProduct( arr, N)
{

    // Stores the resultant product
    let product = 1;

    // Traverse the array arr[]
    for (let i = 0; i < N; i++) {

        // Stores the count
        // of set bits of arr[i]
        let bits = countbits(arr[i]);

        // Update the product
        product *= bits;
    }

    // Return the resultant product
    return product;
}

// Driver Code

let arr = [ 3, 2, 4, 1, 5 ];
let N = arr.length;
document.write(BitProduct(arr, N));

</script>
```

**输出：**

```
4
```

**时间复杂度：** `O(N * log M)`，其中 `M` 是数组的最大元素。
**辅助空间：** `O(1)`