# 给定数组最大化按位异或需要相加的最小值

> 原文: [https://www.geeksforgeeks.org/minimum-value-to-be-added-to-maximize-bitwise-xor-of-the-given-array/](https://www.geeksforgeeks.org/minimum-value-to-be-added-to-maximize-bitwise-xor-of-the-given-array/)

给定一个由 `N` 个整数组成的数组 `arr[]`，任务是找到一个整数 `K`，在任何数组元素中不超过最大位数，当添加到数组中时，最大化数组的位异或。

**示例:**

> **输入:** `N = 7`，`arr[] = {1, 7, 8, 11, 6, 9, 6}`
> **输出:** `3`
> **解释:**
> 给定数组的按位异或 = `1 ^ 7 ^ 8 ^ 11 ^ 6 ^ 9 ^ 6 = 12`
> `(12)₂ = (1100)₂`
> `(0011)₂`
> 因此，`12 ^ 3 = 15` 是给定数组的最大可能异或。
>
> **输入:** `N = 5`，`arr[] = {1, 2, 3, 4, 5}`
> **输出:** `6`
> **解释:**
> 给定数组的按位异或 = `1 ^ 2 ^ 3 ^ 4 ^ 5 = 1`
> `(1)₂ = (0001)₂`
> `(0110)₂ = (6)`
> 因此，`1 ^ 6 = 7` 是给定数组的最大可能异或。

**方法:** 按照以下步骤解决问题:

*   计算数组所有元素的位异或。
*   计算数组元素的计算出的异或的补码，使得补码中的位数等于任意数组元素中存在的最大位数。
*   异或的补码是为最大化给定数组的按位异或而需要添加的值。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find complement of an integer
unsigned int onesComplement(unsigned int n,
                            int maxElement)
{
    // Count the number of bits of maxElement
    int bits = floor(log2(maxElement)) + 1;

    // Return 1's complement
    return ((1 << bits) - 1) ^ n;
}

// Function to find the value required to be
// added to maximize XOR of the given array
int findNumber(int arr[], int n)
{
    // Stores the required value
    // to be added to the array
    unsigned int res = 0;

    // Stores the maximum array element
    int maxElement = 0;

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // Update XOR of the array
        res = res ^ arr[i];

        // Find maximum element in array
        if (maxElement < arr[i])
            maxElement = arr[i];
    }

    // Calculate 1s' complement
    res = onesComplement(res,
                         maxElement);

    // Return the answer
    return (res);
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << findNumber(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;
import java.io.*;
import java.lang.*;

class GFG{

// Function to find complement of an integer
static int onesComplement(int n,
                          int maxElement)
{

    // Count the number of bits of maxElement
    int bits = (int)Math.floor((
                    Math.log(maxElement) /
                    Math.log(2))) + 1 ;

    // Return 1's complement
    return ((1 << bits) - 1) ^ n;
}

// Function to find the value required to be
// added to maximize XOR of the given array
static int findNumber(int arr[], int n)
{

    // Stores the required value
    // to be added to the array
    int res = 0;

    // Stores the maximum array element
    int maxElement = 0;

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Update XOR of the array
        res = res ^ arr[i];

        // Find maximum element in array
        if (maxElement < arr[i])
            maxElement = arr[i];
    }

    // Calculate 1s' complement
    res = onesComplement(res,
                         maxElement);

    // Return the answer
    return (res);
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 1, 2, 3, 4, 5 };
    int N = arr.length;

    System.out.print(findNumber(arr, N));
}
}

// This code is contributed by sanjoy_62
```

## Python 3

```python
# Python program for the above approach
import math

# Function to find complement of an integer
def onesComplement(n, maxElement) :

    # Count the number of bits of maxElement
    bits = math.floor(math.log2(maxElement)) + 1

    # Return 1's complement
    return ((1 << bits) - 1) ^ n

# Function to find the value required to be
# added to maximize XOR of the given array
def findNumber(arr, n) :

    # Stores the required value
    # to be added to the array
    res = 0

    # Stores the maximum array element
    maxElement = 0

    # Traverse the array
    for i in range(n):

        # Update XOR of the array
        res = res ^ arr[i]

        # Find maximum element in array
        if (maxElement < arr[i]):
            maxElement = arr[i]

    # Calculate 1s' complement
    res = onesComplement(res, maxElement)

    # Return the answer
    return (res)

# Driver Code

arr = [ 1, 2, 3, 4, 5 ]
N = len(arr)
print(findNumber(arr, N))

# This code is contributed by code_hunt.
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find complement of an integer
static int onesComplement(int n,
                          int maxElement)
{

    // Count the number of bits of maxElement
    int bits = (int)Math.Floor((
                    Math.Log(maxElement) /
                    Math.Log(2))) + 1 ;

    // Return 1's complement
    return ((1 << bits) - 1) ^ n;
}

// Function to find the value required to be
// added to maximize XOR of the given array
static int findNumber(int[] arr, int n)
{

    // Stores the required value
    // to be added to the array
    int res = 0;

    // Stores the maximum array element
    int maxElement = 0;

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Update XOR of the array
        res = res ^ arr[i];

        // Find maximum element in array
        if (maxElement < arr[i])
            maxElement = arr[i];
    }

    // Calculate 1s' complement
    res = onesComplement(res,
                         maxElement);

    // Return the answer
    return (res);
}

// Driver Code
public static void Main()
{
    int[] arr = { 1, 2, 3, 4, 5 };
    int N = arr.Length;

    Console.Write(findNumber(arr, N));
}
}

// This code is contributed by susmitakundugoaldanga
```

## JavaScript

```javascript
<script>

// JavaScript program for above approach

// Function to find complement of an integer
function onesComplement(n,
                          maxElement)
{

    // Count the number of bits of maxElement
    let bits = Math.floor((
                    Math.log(maxElement) /
                    Math.log(2))) + 1 ;

    // Return 1's complement
    return ((1 << bits) - 1) ^ n;
}

// Function to find the value required to be
// added to maximize XOR of the given array
function findNumber(arr, n)
{

    // Stores the required value
    // to be added to the array
    let res = 0;

    // Stores the maximum array element
    let maxElement = 0;

    // Traverse the array
    for(let i = 0; i < n; i++)
    {

        // Update XOR of the array
        res = res ^ arr[i];

        // Find maximum element in array
        if (maxElement < arr[i])
            maxElement = arr[i];
    }

    // Calculate 1s' complement
    res = onesComplement(res,
                         maxElement);

    // Return the answer
    return (res);
}

// Driver Code
     let arr = [ 1, 2, 3, 4, 5 ];
    let N = arr.length;

    document.write(findNumber(arr, N));

// This code is contributed by avijitmondal1998.
</script>
```

**输出:**

```
6
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`