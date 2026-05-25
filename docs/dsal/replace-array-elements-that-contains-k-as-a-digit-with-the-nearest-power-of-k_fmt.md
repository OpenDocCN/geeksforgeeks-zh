# 将包含 K 的数组元素替换为 K 的最近次幂

> 原文: [https://www.geeksforgeeks.org/replace-array-elements-that-contains-k-as-a-digit-with-the-nearest-power-of-k/](https://www.geeksforgeeks.org/replace-array-elements-that-contains-k-as-a-digit-with-the-nearest-power-of-k/)

给定一个大小为 `N` 的数组 `arr[]` 和一个整数 `K`，任务是将每个由数字 `K` 组成的数组元素替换为最接近的 `K` 的幂。
> **注:** 如果恰好有两个最近的幂，那么取较大的一个。

**示例:**

> **输入:** `arr[] = {432, 953, 232, 333}`, `K = 3`
> **输出:** `{243, 729, 243, 243}`
> **解释:**
> `arr[0] = 3^5 = 243`。
> `arr[1] = 3^6 = 729`。
> `arr[2] = 3^5 = 243`。
> `arr[3] = 3^5 = 243`。
>
> **输入:** `arr[] = {532, 124, 244, 485}`, `K = 4`
> **输出:** `{532, 64, 256, 256}`

## 方法

想法是将数组的每个元素转换成一个字符串，然后在字符串中搜索数字 `K`，如果找到，则用最接近的 `K` 的幂替换它。按照以下步骤解决问题:

*   声明一个函数，求 `K` 的最近幂:
    *   找到最接近元素的 `X^p` 中的 `p` 的值。
    *   计算 `p` 取 `log_X(元素)` 的地板值。
    *   因此，`p` 和 `p+1` 将是可以得到最近幂的两个整数。
    *   计算 `X^K` 和 `X^(K + 1)` 并检查哪个更靠近元素并返回该元素。
*   遍历数组 `arr`:
    *   将每个元素转换为字符串。
    *   遍历字符串并检查数字 `K` 的存在，如果找到，则用最近的 `K` 的幂替换数组元素并从该点断开。
*   打印修改后的数组。

下面是上述方法的实现:

## 代码实现

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate the
// power of base nearest to x
int nearestPow(int x, int base)
{

    // Stores logX to the base K
    int k = int(log(x) / log(base));
    if (abs(pow(base, k) - x) < abs(pow(base, (k + 1)) - x))
        return pow(base, k);
    else
        return pow(base, (k + 1));
}

// Function to replace array
// elements with nearest power of K
void replaceWithNearestPowerOfK(int arr[], int K, int n)
{

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // Convert integer into a string
        string strEle = to_string(arr[i]);

        for (int c = 0; c < strEle.length(); c++) {

            // If K is found, then replace
            // with the nearest power of K
            if ((strEle[c]-'0') == K) {

                arr[i] = nearestPow(arr[i], K);
                break;
            }
        }
    }

    // Print the array
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}
// Driver Code
int main()
{

    // Given array
    int arr[] = { 432, 953, 232, 333 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Given value of K
    int K = 3;

    // Function call to replace array
    // elements with nearest power of K
    replaceWithNearestPowerOfK(arr, K, n);
}

// This code is contributed by ukasp.
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG {

// Function to calculate the
// power of base nearest to x
static int nearestPow(int x, int base1)
{

    // Stores logX to the base K
    int k = (int)(Math.log(x) / Math.log(base1));

    if (Math.abs(Math.pow(base1, k) - x) <
        Math.abs(Math.pow(base1, (k + 1)) - x))
        return (int)Math.pow(base1, k);
    else
        return (int)Math.pow(base1, (k + 1));
}

// Function to replace array
// elements with nearest power of K
static void replaceWithNearestPowerOfK(int []arr, int K,
                                       int n)
{

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Convert integer into a string
        int num = arr[i];
        String strEle = String.valueOf(num);

        for(int c = 0; c < strEle.length(); c++)
        {

            // If K is found, then replace
            // with the nearest power of K
            if ((strEle.charAt(c) - '0') == K)
            {
                arr[i] = nearestPow(arr[i], K);
                break;
            }
        }
    }

    // Print the array
    for(int i = 0; i < n; i++)
        System.out.print(arr[i] + " ");
}

// Driver Code
public static void main (String[] args)
{

    // Given array
    int []arr = { 432, 953, 232, 333 };
    int n = arr.length;

    // Given value of K
    int K = 3;

    // Function call to replace array
    // elements with nearest power of K
    replaceWithNearestPowerOfK(arr, K, n);
}
}

// This code is contributed by avanitrachhadiya2155
```

### Python 3

```python
# Python3 program
# for the above approach
import math

# Function to calculate the
# power of base nearest to x
def nearestPow(x, base):

    # Stores logX to the base K
    k = int(math.log(x, base))

    if abs(base**k - x) < abs(base**(k+1) - x):
        return base**k
    else:
        return base**(k+1)

# Function to replace array
# elements with nearest power of K
def replaceWithNearestPowerOfK(arr, K):

    # Traverse the array
    for i in range(len(arr)):

        # Convert integer into a string
        strEle = str(arr[i])

        for c in strEle:

            # If K is found, then replace
            # with the nearest power of K
            if int(c) == K:
                arr[i] = nearestPow(arr[i], K)
                break

    # Print the array
    print(arr)

# Driver Code

# Given array
arr = [432, 953, 232, 333]

# Given value of K
K = 3

# Function call to replace array
# elements with nearest power of K
replaceWithNearestPowerOfK(arr, K)
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to calculate the
// power of base nearest to x
static int nearestPow(int x, int base1)
{

    // Stores logX to the base K
    int k = (int)(Math.Log(x) / Math.Log(base1));
    if (Math.Abs(Math.Pow(base1, k) - x) < Math.Abs(Math.Pow(base1, (k + 1)) - x))
        return (int)Math.Pow(base1, k);
    else
        return (int)Math.Pow(base1, (k + 1));
}

// Function to replace array
// elements with nearest power of K
static void replaceWithNearestPowerOfK(int []arr, int K, int n)
{

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // Convert integer into a string
        int num = arr[i];
        string strEle = num.ToString();

        for (int c = 0; c < strEle.Length; c++) {

            // If K is found, then replace
            // with the nearest power of K
            if ((strEle[c]-'0') == K) {

                arr[i] = nearestPow(arr[i], K);
                break;
            }
        }
    }

    // Print the array
    for (int i = 0; i < n; i++)
        Console.Write(arr[i]+" ");
}
// Driver Code
public static void Main()
{

    // Given array
    int []arr = { 432, 953, 232, 333 };
    int n = arr.Length;

    // Given value of K
    int K = 3;

    // Function call to replace array
    // elements with nearest power of K
    replaceWithNearestPowerOfK(arr, K, n);
}
}

// This code is contributed by ipg2016107.
```

## java 描述语言

```javascript
<script>

        // Javascript program for the
        // above approach

        // Function to calculate the
        // power of base nearest to x
        function nearestPow( x, base)
        {

            // Stores logX to the base K
            let k =
            Math.floor(Math.log(x) / Math.log(base));

            if (Math.abs(Math.pow(base, k) - x) <
            Math.abs(Math.pow(base, (k + 1)) - x))
                return Math.pow(base, k);
            else
                return Math.pow(base, (k + 1));
        }

        // Function to replace array
        // elements with nearest power of K
        function replaceWithNearestPowerOfK( arr, K, n)
        {

            // Traverse the array
            for (let i = 0; i < n; i++) {

                // Convert integer into a string
                let strEle = arr[i].toString();

                for (let c = 0; c < strEle.length; c++)
                {

                    // If K is found, then replace
                    // with the nearest power of K
                    if ((strEle - '0') == K) {

                        arr[i] = nearestPow(arr[i], K);
                        break;
                    }
                }
            }

            // Print the array
            for (let i = 0; i < n; i++)
            document.write(arr[i] + " ")
        }
        // Driver Code

            // Given array
            let arr = [ 432, 953, 232, 333 ];
            let n = arr.length;

            // Given value of K
            let K = 3;

            // Function call to replace array
            // elements with nearest power of K
            replaceWithNearestPowerOfK(arr, K, n)

        // This code is contributed by Hritik

    </script>
```

### Output

```
[243, 729, 243, 243]
```

### 复杂度分析

**时间复杂度:** `O(N)`
T5**辅助空间:** `O(1)`