# 将一个阵列分成两个子阵列且乘积相等的最小索引

> 原文: [https://www.geeksforgeeks.org/smallest-index-that-splits-an-array-into-two-subarrays-with-equal-product/](https://www.geeksforgeeks.org/smallest-index-that-splits-an-array-into-two-subarrays-with-equal-product/)

## 问题描述

给定一个由 **N 个非零**整数组成的[数组](https://www.geeksforgeeks.org/array-data-structure/)（基于 1 的索引）`arr[]`，任务是找到最左边的索引 `i`，使得子数组 `arr[1, i]` 和 `arr[i+1, N]` 的所有元素的[乘积相同](https://www.geeksforgeeks.org/product-of-all-subarrays-of-an-array/)。

## 示例

**输入:** `arr[] = {1, 2, 3, 3, 2, 1}`
**输出:** 3
**解释:** 索引 3 生成子数组 `{arr[1], arr[3]}`，其乘积为 6（= 1 * 2 * 3），和 `{arr[4], arr[6]}` 的乘积 6（= 3 * 2 * 1）相等。

**输入:** `arr = {3, 2, 6}`
**输出:** 2

## 方法

按照以下步骤解决问题:

1.  初始化一个变量，比如 `product`，存储所有数组元素乘积。
2.  [遍历给定数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，找到所有数组元素的[积，存入 `product`](https://www.geeksforgeeks.org/program-for-product-of-array/)。
3.  将两个变量 `left` 和 `right` 初始化为 `1`，存储左右子阵列的乘积。
4.  [遍历给定数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)并执行以下步骤:
    *   将 `left` 的值乘以 `arr[i]`。
    *   将 `right` 的值除以 `arr[i]`。
    *   如果 `left` 的值等于 `right`，则打印当前索引 `i` 的值作为合成索引，[跳出循环](https://www.geeksforgeeks.org/break-statement-cc/)。
5.  完成上述步骤后，如果没有这样的索引，则打印 `-1` 作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <iostream>
using namespace std;

// Function to find the smallest
// index that splits the array into
// two subarrays with equal product
void prodEquilibrium(int arr[], int N)
{
    // Stores the product of the array
    int product = 1;

    // Traverse the given array
    for (int i = 0; i < N; i++) {
        product *= arr[i];
    }

    // Stores the product of left
    // and the right subarrays
    int left = 1;
    int right = product;

    // Traverse the given array
    for (int i = 0; i < N; i++) {

        // Update the products
        left = left * arr[i];
        right = right / arr[i];

        // Check if product is equal
        if (left == right) {

            // Print resultant index
            cout << i + 1 << endl;
            return;
        }
    }

    // If no partition exists, then
    // print -1.
    cout << -1 << endl;
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 3, 2, 1 };
    int N = sizeof(arr) / sizeof(arr[0]);
    prodEquilibrium(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to find the smallest
// index that splits the array into
// two subarrays with equal product
static void prodEquilibrium(int arr[], int N)
{

    // Stores the product of the array
    int product = 1;

    // Traverse the given array
    for(int i = 0; i < N; i++)
    {
        product *= arr[i];
    }

    // Stores the product of left
    // and the right subarrays
    int left = 1;
    int right = product;

    // Traverse the given array
    for(int i = 0; i < N; i++)
    {

        // Update the products
        left = left * arr[i];
        right = right / arr[i];

        // Check if product is equal
        if (left == right)
        {

            // Print resultant index
            System.out.print(i + 1 + "\n");
            return;
        }
    }

    // If no partition exists, then
    // print -1.
    System.out.print(-1 + "\n");
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 1, 2, 3, 3, 2, 1 };
    int N = arr.length;

    prodEquilibrium(arr, N);
}
}

// This code is contributed by 29AjayKumar
```

### Python 3

```python
# Python 3 program for the above approach

# Function to find the smallest
# index that splits the array into
# two subarrays with equal product
def prodEquilibrium(arr, N):

    # Stores the product of the array
    product = 1

    # Traverse the given array
    for i in range(N):
        product *= arr[i]

    # Stores the product of left
    # and the right subarrays
    left = 1
    right = product

    # Traverse the given array
    for i in range(N):
        # Update the products
        left = left * arr[i]
        right = right // arr[i]

        # Check if product is equal
        if (left == right):
            # Print resultant index
            print(i + 1)
            return

    # If no partition exists, then
    # print -1.
    print(-1)

# Driver Code
if __name__ == '__main__':
    arr = [1, 2, 3, 3, 2, 1]
    N = len(arr)
    prodEquilibrium(arr, N)

    # This code is contributed by ipg2016107.
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG {

    // Function to find the smallest
    // index that splits the array into
    // two subarrays with equal product
    static void prodEquilibrium(int[] arr, int N)
    {

        // Stores the product of the array
        int product = 1;

        // Traverse the given array
        for (int i = 0; i < N; i++) {
            product *= arr[i];
        }

        // Stores the product of left
        // and the right subarrays
        int left = 1;
        int right = product;

        // Traverse the given array
        for (int i = 0; i < N; i++) {

            // Update the products
            left = left * arr[i];
            right = right / arr[i];

            // Check if product is equal
            if (left == right) {

                // Print resultant index
                Console.WriteLine(i + 1 + "\n");
                return;
            }
        }

        // If no partition exists, then
        // print -1.
        Console.WriteLine(-1 + "\n");
    }

    // Driver Code
    public static void Main(string[] args)
    {
        int[] arr = { 1, 2, 3, 3, 2, 1 };
        int N = arr.Length;

        prodEquilibrium(arr, N);
    }
}

 // This code is contributed by ukasp.
```

### JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to find the smallest
// index that splits the array into
// two subarrays with equal product
function prodEquilibrium(arr, N)
{
    // Stores the product of the array
    let product = 1;

    // Traverse the given array
    for (let i = 0; i < N; i++) {
        product *= arr[i];
    }

    // Stores the product of left
    // and the right subarrays
    let left = 1;
    let right = product;

    // Traverse the given array
    for (let i = 0; i < N; i++) {

        // Update the products
        left = left * arr[i];
        right = right / arr[i];

        // Check if product is equal
        if (left == right) {

            // Print resultant index
            document.write((i + 1) + "<br>");
            return;
        }
    }

    // If no partition exists, then
    // print -1.
    document.write((-1) + "<br>");
}

// Driver Code

    let arr = [ 1, 2, 3, 3, 2, 1 ];
    let N = arr.length;
    prodEquilibrium(arr, N);

    // This code is contributed by Dharanendra L V.

</script>
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`