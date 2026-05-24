# 求数组中所有元素的异或

> 原文：[https://www.geeksforgeeks.org/find-xor-of-all-elements-in-an-array/](https://www.geeksforgeeks.org/find-xor-of-all-elements-in-an-array/)

## 问题描述

给定一个包含大小为 `N` 的整数的数组 `arr[]`，任务是找到这个数组的[异或](https://www.geeksforgeeks.org/tag/xor/)。

**举例：**

> **输入：** `arr[] = {2, 4, 7}`
> **输出：** `1`
> **解释：**
> 数组的 xor = `2 ^ 4 ^ 7 = 1`
>
> **输入：** `arr[] = { 3, 9, 12, 13, 15 }`
> **输出：** `4`

## 方法

为了找到数组中所有元素的 XOR，我们简单地迭代数组，并使用 `^` 运算符找到 XOR。因此，按照以下步骤计算答案：

1.  创建一个变量来存储数组的异或结果。
2.  对于数组中的每个元素，使用 `^` 算子求出元素和结果变量的 XOR。
3.  最后，结果变量存储数组中所有元素的异或。

以下是上述方法的实现：

### C++ 实现

```cpp
// C++ program to find the XOR of
// all elements in the array

#include <bits/stdc++.h>
using namespace std;

// Function to find the XOR of
// all elements in the array
int xorOfArray(int arr[], int n)
{
    // Resultant variable
    int xor_arr = 0;

    // Iterating through every element in
    // the array
    for (int i = 0; i < n; i++) {

        // Find XOR with the result
        xor_arr = xor_arr ^ arr[i];
    }

    // Return the XOR
    return xor_arr;
}

// Driver Code
int main()
{

    int arr[] = { 3, 9, 12, 13, 15 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Function call
    cout << xorOfArray(arr, n) << endl;

    return 0;
}
```

### Java 实现

```java
// Java program to find the XOR of
// all elements in the array
class GFG {

    // Function to find the XOR of
    // all elements in the array
    static int xorOfArray(int arr[], int n)
    {
        // Resultant variable
        int xor_arr = 0;

        // Iterating through every element in
        // the array
        for (int i = 0; i < n; i++) {

            // Find XOR with the result
            xor_arr = xor_arr ^ arr[i];
        }

        // Return the XOR
        return xor_arr;
    }

    // Driver Code
    public static void main (String[] args)
    {

        int arr[] = { 3, 9, 12, 13, 15 };
        int n = arr.length;

        // Function call
        System.out.println(xorOfArray(arr, n));

    }
}

// This code is contributed by Yash_R
```

### Python 3 实现

```python
# Python3 program to find the XOR of
# all elements in the array

# Function to find the XOR of
# all elements in the array
def xorOfArray(arr, n):

    # Resultant variable
    xor_arr = 0

    # Iterating through every element in
    # the array
    for i in range(n):

        # Find XOR with the result
        xor_arr = xor_arr ^ arr[i]

    # Return the XOR
    return xor_arr

# Driver Code
if __name__ == '__main__':
    arr = [3, 9, 12, 13, 15]
    n = len(arr)

    # Function call
    print(xorOfArray(arr, n))

# This code is contributed by mohit kumar 29
```

### C# 实现

```csharp
// C# program to find the XOR of
// all elements in the array
using System;

class GFG {

    // Function to find the XOR of
    // all elements in the array
    static int xorOfArray(int []arr, int n)
    {
        // Resultant variable
        int xor_arr = 0;

        // Iterating through every element in
        // the array
        for (int i = 0; i < n; i++) {

            // Find XOR with the result
            xor_arr = xor_arr ^ arr[i];
        }

        // Return the XOR
        return xor_arr;
    }

    // Driver Code
    public static void Main (string[] args)
    {

        int []arr = { 3, 9, 12, 13, 15 };
        int n = arr.Length;

        // Function call
        Console.WriteLine(xorOfArray(arr, n));
    }
}

// This code is contributed by AnkitRai01
```

### JavaScript 实现

```javascript
<script>

// JavaScript program to find the XOR of
// all elements in the array

// Function to find the XOR of
// all elements in the array
function xorOfArray(arr, n)
{
    // Resultant variable
    let xor_arr = 0;

    // Iterating through every element in
    // the array
    for (let i = 0; i < n; i++) {

        // Find XOR with the result
        xor_arr = xor_arr ^ arr[i];
    }

    // Return the XOR
    return xor_arr;
}

// Driver Code
    let arr = [ 3, 9, 12, 13, 15 ];
    let n = arr.length;

    // Function call
    document.write(xorOfArray(arr, n) + "<br>");

// This code is contributed by Surbhi Tyagi.

</script>
```

**Output:**

```
4
```

**时间复杂度：** `O(N)`，其中 `N` 是数组的大小。