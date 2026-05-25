# 将所有数组元素替换为其前一元素的最近次幂

> 原文: [https://www.geeksforgeeks.org/replace-all-array-elements-with-the-nearest-power-of-its-previous-element/](https://www.geeksforgeeks.org/replace-all-array-elements-with-the-nearest-power-of-its-previous-element/)

给定一个由 `N` 个整数组成的[圆形数组](https://www.geeksforgeeks.org/circular-array/) `arr[]`，任务是用其先前相邻元素的最近可能幂替换所有数组元素。

## 示例

**输入:** `arr[] = {2, 4, 6, 3, 11}`
**输出:** `1 4 4 6 9`
**说明:**
离 `2` 最近的 `11` 次方 —> `11^0 = 1`
离 `4` 最近的 `2` 次方 —> `2^2 = 4`
离 `6` 最近的 `4` 次方 —> `4^1 = 4`
离 `3` 最近的 `6` 次方 —> `6^1 = 6`
离 `11` 最近的 `3` 次方 —> `3^2 = 9`

**输入:** `arr[] = {3, 2, 4, 3}`
**输出:** `3 3 4 4`
**解释:**
最接近 `3` 的 `3` 次方 —> `3^1 = 3`
最接近 `2` 的 `3` 次方 —> `3^1 = 3`
最接近 `4` 的 `2` 次方 —> `2^2 = 4`
最接近 `3` 的 `4` 次方 —> `4^1 = 4`

## 方法

解决这个问题的思路是[遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，对于每个数组元素 `arr[i]`，求前一个元素 `X` 的幂，比如说 `X^K` 最接近 `arr[i]`。遵循以下步骤:
*   计算 `K` 的值，等于 `log_x(Y)` 的[向下取整值](https://www.geeksforgeeks.org/ceil-floor-functions-cpp/)。
*   因此，`K` 和 `(K + 1)` 将是幂最接近的两个整数。
*   计算 `X^K` 和 `X^(K + 1)` 并检查哪个更接近 `Y`。然后，打印该值。

下面是上述方法的实现:

## C++

```cpp
// CPP program for the above approach
#include <iostream>
#include <cmath>
using namespace std;

// Function to calculate log x for given base
int LOG(int a, int b) {
    return log(a) / log(b);
}

// Function to replace all array
// elements with the nearest power
// of previous adjacent nelement
void repbyNP(int *arr,int n)
{

    // For the first element, set the last
    // array element to its previous element
    int x = arr[n - 1];

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Find K for which x ^ k is
        // nearest to arr[i]
        int k = LOG(arr[i], x);
        int temp = arr[i];

        // Find the power to x nearest to arr[i]
        if (abs(pow(x,k) - arr[i]) < abs(pow(x,k+1) - arr[i]))
            arr[i] = pow(x, k);
        else
            arr[i] = pow(x, k + 1);

        // Update x
        x = temp;
    }
}
int main()
{

    // Driver Code
    int arr[5] = {2, 4, 6, 3, 11};
    int n = sizeof(arr)/sizeof(arr[0]);

    // Function Call
    repbyNP(arr,n);

    // Display the array
    for(int i = 0; i < n; i++)
        cout<<arr[i]<<" ";
    return 0;
}

// This code is contributed by rohitsingh07052.
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG
{

// Function to calculate log x for given base
static int LOG(int a, int b) {
    return (int)(Math.log(a) / Math.log(b));
}

// Function to replace all array
// elements with the nearest power
// of previous adjacent nelement
static void repbyNP(int[] arr,int n)
{

    // For the first element, set the last
    // array element to its previous element
    int x = arr[n - 1];

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Find K for which x ^ k is
        // nearest to arr[i]
        int k = LOG(arr[i], x);
        int temp = arr[i];

        // Find the power to x nearest to arr[i]
        if (Math.abs(Math.pow(x,k) - arr[i]) < Math.abs(Math.pow(x,k+1) - arr[i]))
            arr[i] = (int)Math.pow(x, k);
        else
            arr[i] = (int)Math.pow(x, k + 1);

        // Update x
        x = temp;
    }
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = {2, 4, 6, 3, 11};
    int n = arr.length;

    // Function Call
    repbyNP(arr,n);

    // Display the array
    for(int i = 0; i < n; i++)
        System.out.print(arr[i] + " ");
}
}

// This code is contributed by sanjoy_62.
```

## Python 3

```python
# Python3 program for the above approach
import math

# Function to calculate log x for given base
def LOG(x, base):
    return int(math.log(x)/math.log(base))

# Function to replace all array
# elements with the nearest power
# of previous adjacent nelement
def repbyNP(arr):

    # For the first element, set the last
    # array element to its previous element
    x = arr[-1]

    # Traverse the array
    for i in range(len(arr)):

        # Find K for which x ^ k is
        # nearest to arr[i]
        k = LOG(arr[i], x)
        temp = arr[i]

        # Find the power to x nearest to arr[i]
        if abs(x**k - arr[i]) < abs(x**(k + 1) - arr[i]):
            arr[i] = x**k
        else:
            arr[i] = x**(k + 1)

        # Update x
        x = temp

    # Return the array
    return arr

# Driver Code
arr = [2, 4, 6, 3, 11]

# Function Call
print(repbyNP(arr))
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate log x for given base
static int LOG(int a, int b) {
    return (int)(Math.Log(a) / Math.Log(b));
}

// Function to replace all array
// elements with the nearest power
// of previous adjacent nelement
static void repbyNP(int[] arr,int n)
{

    // For the first element, set the last
    // array element to its previous element
    int x = arr[n - 1];

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Find K for which x ^ k is
        // nearest to arr[i]
        int k = LOG(arr[i], x);
        int temp = arr[i];

        // Find the power to x nearest to arr[i]
        if (Math.Abs(Math.Pow(x, k) - arr[i]) <
            Math.Abs(Math.Pow(x, k + 1) - arr[i]))
            arr[i] = (int)Math.Pow(x, k);
        else
            arr[i] = (int)Math.Pow(x, k + 1);

        // Update x
        x = temp;
    }
}

// Driver Code
public static void Main(string[] args)
{
    int[] arr = {2, 4, 6, 3, 11};
    int n = arr.Length;

    // Function Call
    repbyNP(arr,n);

    // Display the array
    for(int i = 0; i < n; i++)
        Console.Write(arr[i] + " ");
}
}

// This code is contributed by code_hunt.
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to calculate log x for given base
function LOG(a, b) {
    return parseInt(Math.log(a) / Math.log(b));
}

// Function to replace all array
// elements with the nearest power
// of previous adjacent nelement
function repbyNP(arr, n)
{

    // For the first element, set the last
    // array element to its previous element
    let x = arr[n - 1];

    // Traverse the array
    for(let i = 0; i < n; i++)
    {

        // Find K for which x ^ k is
        // nearest to arr[i]
        let k = LOG(arr[i], x);
        let temp = arr[i];

        // Find the power to x nearest to arr[i]
        if (Math.abs(Math.pow(x, k) - arr[i]) < Math.abs(Math.pow(x, k + 1) - arr[i]))
            arr[i] = Math.pow(x, k);
        else
            arr[i] = Math.pow(x, k + 1);

        // Update x
        x = temp;
    }
}

    // Driver Code
    let arr = [2, 4, 6, 3, 11];
    let n = arr.length;

    // Function Call
    repbyNP(arr, n);

    // Display the array
    for(let i = 0; i < n; i++)
        document.write(arr[i] + " ");

    // This code is contributed by rishavmahato348.
</script>
```

## 输出

```
[1, 4, 4, 1, 9]
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`