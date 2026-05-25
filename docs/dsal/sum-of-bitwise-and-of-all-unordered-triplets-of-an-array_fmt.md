# 数组中所有无序三元组的按位“与”的和

> 原文: [https://www.geeksforgeeks.org/sum-of-bitwise-and-of-all-unordered-triplets-of-an-array/](https://www.geeksforgeeks.org/sum-of-bitwise-and-of-all-unordered-triplets-of-an-array/)

给定一个由`N`个正整数组成的数组`arr[]`，任务是求所有可能三元组`(arr[i]、arr[j]、arr[k])`的位与之和，使得`i < j < k`。

## 示例

> **输入:** `arr[] = {3，5，4，7}`
> **输出:** 5
> **解释:** 所有可能三元组的位与之和=`(3&5&4)+(3&5&7)+(3&4&7)+(5&4&7)= 0+1+0+4 = 5`。
>
> **输入:** `arr[] = {4，4，4}`
> **输出:** 4

## 天真方法

解决给定问题的最简单方法是生成给定数组的所有可能三元组`(i，j，k)`，使得`i < j < k`并打印所有可能三元组的位与之和。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to calculate sum of Bitwise
// AND of all unordered triplets from
// a given array such that (i < j < k)
void tripletAndSum(int arr[], int n)
{
    // Stores the resultant sum of
    // Bitwise AND of all triplets
    int ans = 0;

    // Generate all triplets of
    // (arr[i], arr[j], arr[k])
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            for (int k = j + 1; k < n; k++) {

                // Add Bitwise AND to ans
                ans += arr[i] & arr[j] & arr[k];
            }
        }
    }

    // Print the result
    cout << ans;
}

// Driver Code
int main()
{
    int arr[] = { 3, 5, 4, 7 };
    int N = sizeof(arr) / sizeof(arr[0]);
    tripletAndSum(arr, N);
//This code is contributed by Potta Lokesh
    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG
{

    // Function to calculate sum of Bitwise
    // AND of all unordered triplets from
    // a given array such that (i < j < k)
    public static void tripletAndSum(int arr[], int n)
    {

        // Stores the resultant sum of
        // Bitwise AND of all triplets
        int ans = 0;

        // Generate all triplets of
        // (arr[i], arr[j], arr[k])
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                for (int k = j + 1; k < n; k++) {

                    // Add Bitwise AND to ans
                    ans += arr[i] & arr[j] & arr[k];
                }
            }
        }

        // Print the result
        System.out.println(ans);
    }

    public static void main(String[] args)
    {
        int arr[] = { 3, 5, 4, 7 };
        int N = arr.length;
        tripletAndSum(arr, N);
    }
}

 //This code is contributed by Potta Lokesh
```

### Python 3

```python
# Python3 program for the above approach

# Function to calculate sum of Bitwise
# AND of all unordered triplets from
# a given array such that (i < j < k)
def tripletAndSum(arr, n):

    # Stores the resultant sum of
    # Bitwise AND of all triplets
    ans = 0

    # Generate all triplets of
    # (arr[i], arr[j], arr[k])
    for i in range(n):
        for j in range(i + 1, n, 1):
            for k in range(j + 1, n, 1):

                # Add Bitwise AND to ans
                ans += arr[i] & arr[j] & arr[k]

    # Print the result
    print(ans)

# Driver Code
if __name__ == '__main__':

    arr = [ 3, 5, 4, 7 ]
    N = len(arr)

    tripletAndSum(arr, N)

# This code is contributed by bgangwar59
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

    // Function to calculate sum of Bitwise
    // AND of all unordered triplets from
    // a given array such that (i < j < k)
    public static void tripletAndSum(int[] arr, int n)
    {

        // Stores the resultant sum of
        // Bitwise AND of all triplets
        int ans = 0;

        // Generate all triplets of
        // (arr[i], arr[j], arr[k])
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                for (int k = j + 1; k < n; k++) {

                    // Add Bitwise AND to ans
                    ans += arr[i] & arr[j] & arr[k];
                }
            }
        }

        // Print the result
        Console.WriteLine(ans);
    }

// Driver code
static public void Main()
{
    int[] arr = { 3, 5, 4, 7 };
        int N = arr.Length;
        tripletAndSum(arr, N);
}
}

// This code is contributed by splevel62.
```

### JavaScript

```javascript
<script>
        // JavaScript program for the above approach

        // Function to calculate sum of Bitwise
        // AND of all unordered triplets from
        // a given array such that (i < j < k)
        function tripletAndSum(arr, n) {
            // Stores the resultant sum of
            // Bitwise AND of all triplets
            let ans = 0;

            // Generate all triplets of
            // (arr[i], arr[j], arr[k])
            for (let i = 0; i < n; i++) {
                for (let j = i + 1; j < n; j++) {
                    for (let k = j + 1; k < n; k++) {

                        // Add Bitwise AND to ans
                        ans += arr[i] & arr[j] & arr[k];
                    }
                }
            }

            // Print the result
            document.write(ans);
        }

        // Driver Code

        let arr = [3, 5, 4, 7];
        let N = arr.length
        tripletAndSum(arr, N);

        // This code is contributed by Potta Lokesh
  </script>
```

**输出:**

**时间复杂度:** `O(N^3)`
**辅助空间:** `O(1)`

## 有效方法

上述方法也可以通过考虑数字的二进制表示来优化。按照以下步骤解决问题:

*   初始化一个变量，比如说`sum`为`0`，它存储所有可能三元组的位“与”的合成和。
*   在范围`[0，31]`内循环，并执行以下步骤:
    *   初始化一个变量，将`cnt`设为`0`，该变量存储数组元素的计数，数组元素的`i`位被设置。
    *   遍历给定数组，如果`i`位被设置，那么`cnt`的值增加`1`。
    *   在上述步骤之后，对于所有可能的三元组，`i`位被设置，则它将值`((cnt)C(3) * 2^i)`贡献给合成总和。因此，将该值添加到变量`sum`中。
*   完成上述步骤后，打印`sum`的值作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to calculate sum of Bitwise
// AND of all unordered triplets from
// a given array such that (i < j < k)
int tripletAndSum(int arr[], int n)
{
    // Stores the resultant sum of
    // Bitwise AND of all triplets
    int ans = 0;

    // Traverse over all the bits
    for (int bit = 0; bit < 32; bit++) {
        int cnt = 0;

        // Count number of elements
        // with the current bit set
        for (int i = 0; i < n; i++) {
            if (arr[i] & (1 << bit))
                cnt++;
        }

        // There are (cnt)C(3) numbers
        // with the current bit set and
        // each triplet contributes
        // 2^bit to the result
        ans += (1 << bit) * cnt
               * (cnt - 1) * (cnt - 2) / 6;
    }

    // Return the resultant sum
    return ans;
}

// Driver Code
int main()
{
    int arr[] = { 3, 5, 4, 7 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << tripletAndSum(arr, N);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to calculate sum of Bitwise
// AND of all unordered triplets from
// a given array such that (i < j < k)
static int tripletAndSum(int[] arr, int n)
{

    // Stores the resultant sum of
    // Bitwise AND of all triplets
    int ans = 0;

    // Traverse over all the bits
    for(int bit = 0; bit < 32; bit++)
    {
        int cnt = 0;

        // Count number of elements
        // with the current bit set
        for(int i = 0; i < n; i++)
        {
            if ((arr[i] & (1 << bit)) != 0)
                cnt++;
        }

        // There are (cnt)C(3) numbers
        // with the current bit set and
        // each triplet contributes
        // 2^bit to the result
        ans += (1 << bit) * cnt *
               (cnt - 1) * (cnt - 2) / 6;
    }

    // Return the resultant sum
    return ans;
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 3, 5, 4, 7 };
    int N = arr.length;

    System.out.print(tripletAndSum(arr, N));
}
}

// This code is contributed by subham348
```

## 蟒蛇 3

```python
# Python program for the above approach
# Function to calculate sum of Bitwise
# AND of all unordered triplets from
# a given array such that (i < j < k)
def tripletAndSum(arr, n):

    # Stores the resultant sum of
    # Bitwise AND of all triplets
    ans = 0

    # Traverse over all the bits
    for bit in range(32):
        cnt = 0

        # Count number of elements
        # with the current bit set
        for i in range(n):
            if(arr[i] & (1 << bit)):
                cnt+=1

        # There are (cnt)C(3) numbers
        # with the current bit set and
        # each triplet contributes
        # 2^bit to the result
        ans += (1 << bit) * cnt * (cnt - 1) * (cnt - 2) // 6

    # Return the resultant sum
    return ans

# Driver Code
arr =  [3, 5, 4, 7]
N = len(arr)
print(tripletAndSum(arr, N))

# this code is contributed by shivanisinghss2110
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate sum of Bitwise
// AND of all unordered triplets from
// a given array such that (i < j < k)
static int tripletAndSum(int[] arr, int n)
{

    // Stores the resultant sum of
    // Bitwise AND of all triplets
    int ans = 0;

    // Traverse over all the bits
    for(int bit = 0; bit < 32; bit++)
    {
        int cnt = 0;

        // Count number of elements
        // with the current bit set
        for(int i = 0; i < n; i++)
        {
            if ((arr[i] & (1 << bit)) != 0)
                cnt++;
        }

        // There are (cnt)C(3) numbers
        // with the current bit set and
        // each triplet contributes
        // 2^bit to the result
        ans += (1 << bit) * cnt * (cnt - 1) *
                                      (cnt - 2) / 6;
    }

    // Return the resultant sum
    return ans;
}

// Driver Code
public static void Main()
{
    int[] arr = { 3, 5, 4, 7 };
    int N = arr.Length;

    Console.Write(tripletAndSum(arr, N));
}
}

// This code is contributed by rishavmahato348
```

## java 描述语言

```javascript
<script>

// Javascript program for the above approach

// Function to calculate sum of Bitwise
// AND of all unordered triplets from
// a given array such that (i < j < k)
function tripletAndSum(arr, n) {
    // Stores the resultant sum of
    // Bitwise AND of all triplets
    let ans = 0;

    // Traverse over all the bits
    for (let bit = 0; bit < 32; bit++) {
        let cnt = 0;

        // Count number of elements
        // with the current bit set
        for (let i = 0; i < n; i++) {
            if (arr[i] & (1 << bit))
                cnt++;
        }

        // There are (cnt)C(3) numbers
        // with the current bit set and
        // each triplet contributes
        // 2^bit to the result
        ans += (1 << bit) * cnt
            * (cnt - 1) * (cnt - 2) / 6;
    }

    // Return the resultant sum
    return ans;
}

// Driver Code

let arr = [3, 5, 4, 7];
let N = arr.length;
document.write(tripletAndSum(arr, N));

// This code is contributed by _saurabh_jaiswal.
</script>
```

**Output:**

**时间复杂度:** O(N)
**辅助空间:** O(1)