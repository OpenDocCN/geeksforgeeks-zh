# 检查数组是否可以拆分为子数组，使得这些子数组的最长递减子序列的长度的异或为 0

> 原文: [https://www.geeksforgeeks.org/check-if-array-can-be-split-into-subarrays-such-that-xor-of-length-of-longest-decreasing-subsequences-of-those-subarrays-is-0/](https://www.geeksforgeeks.org/check-if-array-can-be-split-into-subarrays-such-that-xor-of-length-of-longest-decreasing-subsequences-of-those-subarrays-is-0/)

给定大小为 `N` 的整数数组 `arr[]`，任务是检查 `arr[]` 是否可以分割成不同的子数组，使得在对所有子数组的 LDS（最长递减子序列）的长度进行异或时等于 `0`。打印 `'YES'` 如果可以拆分，否则打印 `'NO'`。

**示例:**

> **输入:** `arr[] = {1, 0, 3, 4, 5}`
> **输出:** YES
> **解释:** `{1}`、`{0}`、`{3}`、`{4, 5}` 子数组的 LDS 长度: 1, 1, 1, 1，长度的 XOR = 0。所以答案是肯定的。
>
> **输入:** `arr[] = {5, 4, 3}`
> **输出:** NO

**逼近:** 偶数个 `1` 的异或运算为 `0`。所以如果数组长度是偶数，那么每个元素可以被认为是大小为 `1` 的 LDS，这使得偶数个 `1` 的异或等于 `0`。对于奇数长度的数组，任何大小为 `2` 的、具有偶数个 LDS 的子数组都可以被认为是 LDS，即子数组应该严格增加，所以 LDS 将是 `1`。按照以下步骤解决问题:

*   初始化一个变量 `found` 为 `false`。
*   如果 `N` 为偶数，则打印 `'YES'` 并返回。
*   否则，使用变量 `i` 迭代范围 `(0, N–1)`，并执行以下任务:
    *   通过 `arr[i] > arr[i-1]` 检查是否有连续增加的元素。
    *   如果 `arr[i] > arr[i-1]`，使 `found` 为 `true` 并跳出循环。
*   如果 `found` 是 `true`，打印 `"YES"`，否则打印 `"NO"`。

下面是上述方法的实现。

## C++

```cpp
// C++ code for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find XOR of LDS's
// of subarrays
void xor_of_lds(int arr[], int n)
{

    // If length is even each element
    // can be considered as lds of length
    // 1 which makes even 1's and xor is 0
    if (n % 2 == 0) {
        cout << "YES" << endl;
        return;
    }
    else {

        // For odd length we need to find
        // even subarray of length 2 which
        // is strictly increasing so that it
        // makes a subarray with lds=1

        bool found = 0;
        for (int i = 1; i < n; i++) {

            // Check if there are 2
            // consecutive increasing elements
            if (arr[i] > arr[i - 1]) {
                found = 1;
                break;
            }
        }
        if (found == 1)
            cout << "YES" << endl;
        else
            cout << "NO" << endl;
    }
}

// Driver Code
int main()
{

    // Initializing array of arr
    int arr[] = { 1, 0, 3, 4, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Call the function
    xor_of_lds(arr, N);

    return 0;
}
```

## Java

```java
// Java code for the above approach
import java.util.*;
class GFG{

// Function to find XOR of LDS's
// of subarrays
static void xor_of_lds(int arr[], int n)
{

    // If length is even each element
    // can be considered as lds of length
    // 1 which makes even 1's and xor is 0
    if (n % 2 == 0) {
        System.out.print("YES" +"\n");
        return;
    }
    else {

        // For odd length we need to find
        // even subarray of length 2 which
        // is strictly increasing so that it
        // makes a subarray with lds=1

        boolean found = false;
        for (int i = 1; i < n; i++) {

            // Check if there are 2
            // consecutive increasing elements
            if (arr[i] > arr[i - 1]) {
                found = true;
                break;
            }
        }
        if (found == true)
            System.out.print("YES" +"\n");
        else
            System.out.print("NO" +"\n");
    }
}

// Driver Code
public static void main(String[] args)
{

    // Initializing array of arr
    int arr[] = { 1, 0, 3, 4, 5 };
    int N = arr.length;

    // Call the function
    xor_of_lds(arr, N);

}
}

// This code is contributed by shikhasingrajput
```

## Python 3

```python
# Python code for the above approach

# Function to find XOR of LDS's
# of subarrays
def xor_of_lds (arr, n) :

    # If length is even each element
    # can be considered as lds of length
    # 1 which makes even 1's and xor is 0
    if (n % 2 == 0):
        print("YES")
        return
    else:

        # For odd length we need to find
        # even subarray of length 2 which
        # is strictly increasing so that it
        # makes a subarray with lds=1

        found = 0
        for i in range(1, n):
            # Check if there are 2
            # consecutive increasing elements
            if (arr[i] > arr[i - 1]):
                found = 1
                break
        if (found == 1):
            print("YES")
        else:
            print("NO")

# Driver Code
# Initializing array of arr
arr = [1, 0, 3, 4, 5]
N = len(arr)

# Call the function
xor_of_lds(arr, N)

# This code is contributed by Saurabh Jaiswal
```

## C#

```csharp
// C# code for the above approach
using System;

class GFG
{

// Function to find XOR of LDS's
// of subarrays
static void xor_of_lds(int []arr, int n)
{

    // If length is even each element
    // can be considered as lds of length
    // 1 which makes even 1's and xor is 0
    if (n % 2 == 0) {
        Console.Write("YES" + "\n");
        return;
    }
    else {

        // For odd length we need to find
        // even subarray of length 2 which
        // is strictly increasing so that it
        // makes a subarray with lds=1

        bool found = false;
        for (int i = 1; i < n; i++) {

            // Check if there are 2
            // consecutive increasing elements
            if (arr[i] > arr[i - 1]) {
                found = true;
                break;
            }
        }
        if (found == true)
            Console.Write("YES" +"\n");
        else
            Console.Write("NO" +"\n");
    }
}

// Driver Code
public static void Main()
{

    // Initializing array of arr
    int []arr = { 1, 0, 3, 4, 5 };
    int N = arr.Length;

    // Call the function
    xor_of_lds(arr, N);
}
}

// This code is contributed by Samim Hossain Mondal.
```

## JavaScript

```javascript
<script>
    // JavaScript code for the above approach

    // Function to find XOR of LDS's
    // of subarrays
    const xor_of_lds = (arr, n) => {

        // If length is even each element
        // can be considered as lds of length
        // 1 which makes even 1's and xor is 0
        if (n % 2 == 0) {
            document.write("YES<br/>");
            return;
        }
        else {

            // For odd length we need to find
            // even subarray of length 2 which
            // is strictly increasing so that it
            // makes a subarray with lds=1

            let found = 0;
            for (let i = 1; i < n; i++) {

                // Check if there are 2
                // consecutive increasing elements
                if (arr[i] > arr[i - 1]) {
                    found = 1;
                    break;
                }
            }
            if (found == 1)
                document.write("YES<br/>");
            else
                document.write("NO<br/>");
        }
    }

    // Driver Code
    // Initializing array of arr
    let arr = [1, 0, 3, 4, 5];
    let N = arr.length;

    // Call the function
    xor_of_lds(arr, N);

    // This code is contributed by rakeshsahni
</script>
```

**Output**

```
YES
```

时间复杂度: O(N)
辅助空间: O(1)