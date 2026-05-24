# 求每个数组元素最近的 2 次幂

> 原文: [https://www.geeksforgeeks.org/find-the-nearest-power-of-2-for-every-array-element/](https://www.geeksforgeeks.org/find-the-nearest-power-of-2-for-every-array-element/)

给定一个大小为 `N` 的数组 `arr[]`，任务是为每个数组元素打印最近的 2 的次方。
***注:*** 如果恰好有两个最近的 2 的幂，可以考虑大一点的。

**示例:**

> **输入:** `arr[] = {5，2，7，12}`
> **输出:** `4 2 8 16`
> **解释:**
> `arr[0]`(= 5)的最近幂是 4。
> `arr[1]`(= 2)的最近幂是 2。
> `arr[2]`(= 7)的最近幂是 8。
> `arr[3]`(= 12)的最近幂是 8 和 16。打印 16 个，因为它是最大的。
>
> **输入:** `arr[] = {31，13，64}`
> **输出:** `32 16 64`

**方法:** 按照以下步骤解决问题:

*   从左到右遍历数组。
*   对于每个数组元素，求最近的大于和小于它的 2 的幂，即计算 `pow(2，log2(arr[i]))` 和 `pow(2，log2(arr[i]) + 1)`。
*   根据当前数组元素计算这两个值的差，并按照问题陈述中的指定打印最近的值。

下面是上述方法的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find nearest power of two
// for every element in the given array
void nearestPowerOfTwo(int arr[], int N)
{

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // Calculate log of the
        // current array element
        int lg = log2(arr[i]);
        int a = pow(2, lg);
        int b = pow(2, lg + 1);

        // Find the nearest
        if ((arr[i] - a) < (b - arr[i]))
            cout << a << " ";
        else
            cout << b << " ";
    }
}

// Driver Code
int main()
{
    int arr[] = { 5, 2, 7, 12 };
    int N = sizeof(arr) / sizeof(arr[0]);
    nearestPowerOfTwo(arr, N);
    return 0;
}
```

## Java

```java
// Java program to implement the above approach
import java.io.*;

class GFG {

    // Function to find the nearest power of two
    // for every element of the given array
    static void nearestPowerOfTwo(int[] arr, int N)
    {

        // Traverse the array
        for (int i = 0; i < N; i++) {

            // Calculate log of the
            // current array element
            int lg = (int)(Math.log(arr[i])
                           / Math.log(2));

            int a = (int)(Math.pow(2, lg));
            int b = (int)(Math.pow(2, lg + 1));

            // Find the nearest
            if ((arr[i] - a) < (b - arr[i]))
                System.out.print(a + " ");
            else
                System.out.print(b + " ");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int[] arr = { 5, 2, 7, 12 };
        int N = arr.length;
        nearestPowerOfTwo(arr, N);
    }
}
```

## Python 3

```python
# Python program to implement the above approach
import math

# Function to find the nearest power
# of two for every array element
def nearestPowerOfTwo(arr, N):

    # Traverse the array
    for i in range(N):

        # Calculate log of current array element
        lg = (int)(math.log2(arr[i]))

        a = (int)(math.pow(2, lg))
        b = (int)(math.pow(2, lg + 1))

        # Find the nearest
        if ((arr[i] - a) < (b - arr[i])):
            print(a, end = " ")
        else:
            print(b, end = " ")

# Driver Code
arr = [5, 2, 7, 12]
N = len(arr)
nearestPowerOfTwo(arr, N)
```

## C#

```csharp
// C# program to implement the above approach
using System;

class GFG {

    // Function to find nearest power of two
    // for every array element
    static void nearestPowerOfTwo(int[] arr, int N)
    {

        // Traverse the array
        for (int i = 0; i < N; i++) {

            // Calculate log of the
            // current array element
            int lg = (int)(Math.Log(arr[i])
                           / Math.Log(2));

            int a = (int)(Math.Pow(2, lg));
            int b = (int)(Math.Pow(2, lg + 1));

            // Find the nearest
            if ((arr[i] - a) < (b - arr[i]))
                Console.Write(a + " ");
            else
                Console.Write(b + " ");
        }
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int[] arr = { 5, 2, 7, 12 };
        int N = arr.Length;
        nearestPowerOfTwo(arr, N);
    }
}
```

## JavaScript

```javascript
<script>

// JavaScript program to implement
// the above approach

    // Function to find the nearest power of two
    // for every element of the given array
    function nearestPowerOfTwo(arr , N) {

        // Traverse the array
        for (i = 0; i < N; i++) {

            // Calculate log of the
            // current array element
            var lg = parseInt( (Math.log(arr[i]) / Math.log(2)));
            var a = parseInt( (Math.pow(2, lg)));
            var b = parseInt( (Math.pow(2, lg + 1)));

            // Find the nearest
            if ((arr[i] - a) < (b - arr[i]))
                document.write(a + " ");
            else
                document.write(b + " ");
        }
    }

    // Driver Code

        var arr = [ 5, 2, 7, 12 ];
        var N = arr.length;
        nearestPowerOfTwo(arr, N);

// This code is contributed by todaysgaurav

</script>
```

**输出:**

```
4 2 8 16
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`