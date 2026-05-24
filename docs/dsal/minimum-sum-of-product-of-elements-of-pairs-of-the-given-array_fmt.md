# 给定数组对的元素乘积的最小和

> 原文: [https://www.geeksforgeeks.org/minimum-sum-of-product-of-elements-of-pairs-of-the-given-array/](https://www.geeksforgeeks.org/minimum-sum-of-product-of-elements-of-pairs-of-the-given-array/)

给定一个偶数元素 `N` 的数组 `arr[]`。任务是形成 `N/2` 对，使得这些对中元素的乘积之和最小。

## 示例

> **输入:** `arr[] = { 1, 6, 3, 1, 7, 8 }`
> **输出:** `270`
> **解释:**
> 形成的对是 `{1, 1}`，`{3, 6}`，`{7, 8}`
> 这些对之和的乘积 = `2 * 9 * 15 = 270`

> **输入:** `arr[] = {2, 3, 90, 12}`

## 进场

*   对给定的数组 `arr[]` 中的元素进行排序。
*   先配对两个元素，然后再配对下一个元素，以此类推。
*   计算形成的相应对的乘积之和。

以下是上述方法的实现：

## C++

```cpp
// C++ program to find the minimum
// product of sum of pair of element
// in array arr[]
#include "bits/stdc++.h"
using namespace std;

// Function to find the minimum
// product
int minimumProduct(int* arr, int n)
{

    // Sort the array using STL
    // sort() function
    sort(arr, arr + n);

    // Initialise product to 1
    int product = 1;

    for (int i = 0; i < n; i += 2) {

        // Find product of sum of
        // all pairs
        product *= (arr[i] + arr[i + 1]);
    }

    // Return the product
    return product;
}

// Driver code
int main()
{
    int arr[] = { 1, 6, 3, 1, 7, 8 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Function call to find product
    cout << minimumProduct(arr, n) << endl;
    return 0;
}
```

## Java

```java
// Java program to find the minimum
// product of sum of pair of element
// in array arr[]
import java.util.*;

class GFG{

// Function to find the minimum
// product
static int minimumProduct(int[] arr, int n)
{

    // Sort the array using STL
    // sort() function
    Arrays.sort(arr);

    // Initialise product to 1
    int product = 1;

    for (int i = 0; i < n; i += 2) {

        // Find product of sum of
        // all pairs
        product *= (arr[i] + arr[i + 1]);
    }

    // Return the product
    return product;
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 1, 6, 3, 1, 7, 8 };
    int n = arr.length;

    // Function call to find product
    System.out.print(minimumProduct(arr, n) +"\n");
}
}

// This code is contributed by sapnasingh4991
```

## Python 3

```python
# Python3 program to find the minimum
# product of sum of pair of element
# in array arr[]

# Function to find the minimum
# product
def minimumProduct(arr, n):

    # Sort the array using STL
    # sort() function
    arr = sorted(arr)

    # Initialise product to 1
    product = 1

    for i in range(0, n, 2):

        # Find product of sum of
        # all pairs
        product *= (arr[i] + arr[i + 1])

    # Return the product
    return product

# Driver code

arr = [1, 6, 3, 1, 7, 8]
n = len(arr)

# Function call to find product
print(minimumProduct(arr, n))

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program to find the minimum
// product of sum of pair of element
// in array arr[]
using System;

class GFG {

    // Function to find the minimum
    // product
    static int minimumProduct(int[] arr, int n)
    {

        // Sort the array
        // sort() function
        Array.Sort(arr);

        // Initialise product to 1
        int product = 1;

        for (int i = 0; i < n; i += 2) {

            // Find product of sum of
            // all pairs
            product *= (arr[i] + arr[i + 1]);
        }

        // Return the product
        return product;
    }

    // Driver code
    static void Main()
    {
        int[] arr = new int[] { 1, 6, 3, 1, 7, 8 };
        int n = arr.Length;

        // Function call to find product
        Console.Write(minimumProduct(arr, n));
    }
}

// This code is contributed by shubhamsingh10
```

## JavaScript

```javascript
<script>
// Javascript program to find the minimum
// product of sum of pair of element
// in array arr[]

// Function to find the minimum
// product
function minimumProduct(arr, n)
{

    // Sort the array using STL
    // sort() function
    arr.sort();

    // Initialise product to 1
    let product = 1;

    for (let i = 0; i < n; i += 2) {

        // Find product of sum of
        // all pairs
        product *= (arr[i] + arr[i + 1]);
    }

    // Return the product
    return product;
}

// Driver code
    let arr = [ 1, 6, 3, 1, 7, 8 ];
    let n = arr.length;

    // Function call to find product
    document.write(minimumProduct(arr, n) + "<br>");

// This code is contributed by Mayank Tyagi

</script>
```

**输出:**

```
270
```

**时间复杂度:** `O(N * log N)`
**辅助空间:** `O(1)`