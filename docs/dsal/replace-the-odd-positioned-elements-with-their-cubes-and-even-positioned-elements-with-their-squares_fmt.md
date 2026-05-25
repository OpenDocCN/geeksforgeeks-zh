# 用立方体替换奇数位置的元素，用正方形替换偶数位置的元素

> 原文: [https://www.geeksforgeeks.org/replace-the-odd-positioned-elements-with-their-cubes-and-even-positioned-elements-with-their-squares/](https://www.geeksforgeeks.org/replace-the-odd-positioned-elements-with-their-cubes-and-even-positioned-elements-with-their-squares/)

## 问题描述

给定一个由 `n` 个元素组成的数组 `arr[]`，任务是用它们的立方体替换所有奇数位置的元素，用它们的正方形替换偶数位置的元素，即得到的数组必须是 `{arr[0]^3, arr[1]^2, arr[2]^3, arr[3]^2, …}`。

## 示例

**输入:** `arr[] = {2, 3, 4, 5}`
**输出:** `8 9 64 25`
更新后的数组将为 `{2^3, 3^2, 4^3, 5^2} -> {8, 9, 64, 25}`

**输入:** `arr[] = {3, 4, 5, 2}`

## 方法

对于数组 `arr[i]` 中的任何元素，只有当 `(i + 1)` 为奇数时，它才是奇数位置，因为索引从 `0` 开始。现在，遍历数组，用立方体替换所有奇数位置的元素，用正方形替换偶数位置的元素。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;
#define ll long long int

// Utility function to print
// the contents of an array
void printArr(ll arr[], int n)
{
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}

// Function to update the array
void updateArr(ll arr[], int n)
{
    for (int i = 0; i < n; i++) {

        // In case of even positioned element
        if ((i + 1) % 2 == 0)
            arr[i] = (ll)pow(arr[i], 2);

        // Odd positioned element
        else
            arr[i] = (ll)pow(arr[i], 3);
    }

    // Print the updated array
    printArr(arr, n);
}

// Driver code
int main()
{
    ll arr[] = { 2, 3, 4, 5, 6 };
    int n = sizeof(arr) / sizeof(arr[0]);

    updateArr(arr, n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
import java.lang.Math;

class GFG
{

// Utility function to print
// the contents of an array
static void printArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        System.out.print(arr[i] + " ");
}

// Function to update the array
static void updateArr(int arr[], int n)
{
    for (int i = 0; i < n; i++)
    {

        // In case of even positioned element
        if ((i + 1) % 2 == 0)
            arr[i] = (int)Math.pow(arr[i], 2);

        // Odd positioned element
        else
            arr[i] = (int)Math.pow(arr[i], 3);
    }

    // Print the updated array
    printArr(arr, n);
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 2, 3, 4, 5, 6 };
    int n = arr.length;

    updateArr(arr, n);
}
}

// This code is contributed
// by Code_Mech.
```

## Python 3

```python
# Python3 implementation of the approach

# Utility function to print
# the contents of an array
def printArr(arr,n):
    for i in range(n):
        print(arr[i], end = " ")

# Function to update the array
def updateArr(arr, n):
    for i in range(n):

        # In case of even positioned element
        if ((i + 1) % 2 == 0):
            arr[i] = pow(arr[i], 2)

        # Odd positioned element
        else:
            arr[i] = pow(arr[i], 3)

    # Print the updated array
    printArr(arr, n)

# Driver code
arr = [ 2, 3, 4, 5, 6 ]
n = len(arr)

updateArr(arr, n)

# This code is contributed
# by mohit kumar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

// Utility function to print
// the contents of an array
static void printArr(int []arr, int n)
{
    for (int i = 0; i < n; i++)
        Console.Write(arr[i] + " ");
}

// Function to update the array
static void updateArr(int []arr, int n)
{
    for (int i = 0; i < n; i++)
    {

        // In case of even positioned element
        if ((i + 1) % 2 == 0)
            arr[i] = (int)Math.Pow(arr[i], 2);

        // Odd positioned element
        else
            arr[i] = (int)Math.Pow(arr[i], 3);
    }

    // Print the updated array
    printArr(arr, n);
}

// Driver code
public static void Main(String[] args)
{
    int []arr = { 2, 3, 4, 5, 6 };
    int n = arr.Length;

    updateArr(arr, n);
}
}

/* This code contributed by PrinciRaj1992 */
```

## PHP

```php
<?php
// PHP implementation of the approach

// Utility function to print
// the contents of an array
function printArr($arr, $n)
{
    for ($i = 0; $i < $n; $i++)
        echo $arr[$i] . " ";
}

// Function to update the array
function updateArr($arr, $n)
{
    for ($i = 0; $i < $n; $i++)
    {

        // In case of even positioned element
        if (($i + 1) % 2 == 0)
            $arr[$i] = pow($arr[$i], 2);

        // Odd positioned element
        else
            $arr[$i] = pow($arr[$i], 3);
    }

    // Print the updated array
    printArr($arr, $n);
}

// Driver code
$arr = array( 2, 3, 4, 5, 6 );
$n = count($arr);

updateArr($arr, $n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
// javascript implementation of the approach

    // Utility function to print
    // the contents of an array
    function printArr(arr , n) {
        for (i = 0; i < n; i++)
            document.write(arr[i] + " ");
    }

    // Function to update the array
    function updateArr(arr , n) {
        for (i = 0; i < n; i++) {

            // In case of even positioned element
            if ((i + 1) % 2 == 0)
                arr[i] = parseInt( Math.pow(arr[i], 2));

            // Odd positioned element
            else
                arr[i] = parseInt( Math.pow(arr[i], 3));
        }

        // Print the updated array
        printArr(arr, n);
    }

    // Driver code

        var arr = [ 2, 3, 4, 5, 6 ];
        var n = arr.length;

        updateArr(arr, n);

// This code contributed by gauravrajput1
</script>
```

**输出:**

```
8 9 64 25 216
```

**时间复杂度:** `O(n)`

**辅助空间:** `O(1)`