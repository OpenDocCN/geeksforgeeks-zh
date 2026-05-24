# 可被给定数字 K 整除的数组中所有元素的乘积

> 原文: [https://www.geeksforgeeks.org/product-of-all-the-elements-in-an-array-divisible-by-a-given-number-k/](https://www.geeksforgeeks.org/product-of-all-the-elements-in-an-array-divisible-by-a-given-number-k/)

给定一个包含 `N` 个元素和一个数 `k` 的数组，任务是找出该数组中所有可被 `k` 整除的元素的乘积。

**示例**:

```
Input : arr[] = {15, 16, 10, 9, 6, 7, 17}
        K = 3
Output : 810

Input : arr[] = {5, 3, 6, 8, 4, 1, 2, 9}
        K = 2
Output : 384 
```

这个想法是遍历数组并逐个检查元素。如果一个元素可以被 `K` 整除，那么就把这个元素的值乘以到目前为止的乘积，并在到达数组末尾时继续这个过程。下面是上述方法的实现：

## C++

```cpp
// C++ program to find Product of all the elements
// in an array divisible by a given number K

#include <iostream>
using namespace std;

// Function to find Product of all the elements
// in an array divisible by a given number K
int findProduct(int arr[], int n, int k)
{
    int prod = 1;

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // If current element is divisible by k
        // multiply with product so far
        if (arr[i] % k == 0) {
            prod *= arr[i];
        }
    }

    // Return calculated product
    return prod;
}

// Driver code
int main()
{
    int arr[] = { 15, 16, 10, 9, 6, 7, 17 };
    int n = sizeof(arr) / sizeof(arr[0]);
    int k = 3;

    cout << findProduct(arr, n, k);

    return 0;
}
```

## Java

```java
// Java program to find Product of all the elements
// in an array divisible by a given number K

import java.io.*;

class GFG {

// Function to find Product of all the elements
// in an array divisible by a given number K
static int findProduct(int arr[], int n, int k)
{
    int prod = 1;

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // If current element is divisible by k
        // multiply with product so far
        if (arr[i] % k == 0) {
            prod *= arr[i];
        }
    }

    // Return calculated product
    return prod;
}

// Driver code
    public static void main (String[] args) {
        int arr[] = { 15, 16, 10, 9, 6, 7, 17 };
    int n = arr.length;
    int k = 3;

    System.out.println(findProduct(arr, n, k));
    }
}

// This code is contributed by inder_verma..
```

## Python 3

```python
# Python3 program to find Product of all
# the elements in an array divisible by
# a given number K

# Function to find Product of all the elements
# in an array divisible by a given number K
def findProduct(arr, n, k):

    prod = 1

    # Traverse the array
    for i in range(n):

        # If current element is divisible
        # by k, multiply with product so far
        if (arr[i] % k == 0):
            prod *= arr[i]

    # Return calculated product
    return prod

# Driver code
if __name__ == "__main__":

    arr= [15, 16, 10, 9, 6, 7, 17 ]
    n = len(arr)
    k = 3

    print (findProduct(arr, n, k))

# This code is contributed by ita_c
```

## C#

```csharp
// C# program to find Product of all
// the elements in an array divisible
// by a given number K
using System;

class GFG
{

// Function to find Product of all
// the elements in an array divisible
// by a given number K
static int findProduct(int []arr, int n, int k)
{
    int prod = 1;

    // Traverse the array
    for (int i = 0; i < n; i++)
    {

        // If current element is divisible
        // by k multiply with product so far
        if (arr[i] % k == 0)
        {
            prod *= arr[i];
        }
    }

    // Return calculated product
    return prod;
}

// Driver code
public static void Main()
{
    int []arr = { 15, 16, 10, 9, 6, 7, 17 };
    int n = arr.Length;
    int k = 3;

    Console.WriteLine(findProduct(arr, n, k));
}
}

// This code is contributed by inder_verma
```

## PHP

```php
<?php
// PHP program to find Product of
// all the elements in an array
// divisible by a given number K

// Function to find Product of
// all the elements in an array
// divisible by a given number K
function findProduct(&$arr, $n, $k)
{
    $prod = 1;

    // Traverse the array
    for ($i = 0; $i < $n; $i++)
    {

        // If current element is divisible 
        // by k multiply with product so far
        if ($arr[$i] % $k == 0)
        {
            $prod *= $arr[$i];
        }
    }

    // Return calculated product
    return $prod;
}

// Driver code
$arr = array(15, 16, 10, 9, 6, 7, 17 );
$n = sizeof($arr);
$k = 3;

echo (findProduct($arr, $n, $k));

// This code is contributed
// by Shivi_Aggarwal
?>
```

## JavaScript

```javascript
<script>
// Function to find Product of all the elements
// in an array divisible by a given number K
function findProduct( arr, n,  k)
{
    var prod = 1;

    // Traverse the array
    for (var i = 0; i < n; i++) {

        // If current element is divisible by k
        // multiply with product so far
        if (arr[i] % k == 0) {
            prod *= arr[i];
        }
    }

    // Return calculated product
    return prod;
}

var arr = [15, 16, 10, 9, 6, 7, 17 ];

    document.write(findProduct(arr, 7, 3));

</script>
```

**Output:** 

```

```

## 时间复杂度
: `O(N)`，其中 `N` 为数组中的元素个数。

## 辅助空间
: `O(1)`