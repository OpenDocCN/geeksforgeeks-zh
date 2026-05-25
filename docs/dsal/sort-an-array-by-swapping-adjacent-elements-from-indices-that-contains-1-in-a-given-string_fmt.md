# 通过交换给定字符串中包含“1”的索引的相邻元素来对数组进行排序

> 原文: [https://www.geeksforgeeks.org/sort-an-array-by-swapping-adjacent-elements-from-indices-that-contains-1-in-a-given-string/](https://www.geeksforgeeks.org/sort-an-array-by-swapping-adjacent-elements-from-indices-that-contains-1-in-a-given-string/)

给定一个大小为 `N` 的数组 `arr[]` 和一个二进制字符串 `S`，任务是检查是否有可能通过交换相邻的数组元素来对数组 `arr[]` 进行排序，比如说 `arr[i]` 和 `arr[i + 1]`，如果 `S[i]` 等于 `‘1’`。如果可以，那么打印 `“Yes”`。否则，打印 `“No”`。

**示例:**

> **输入:** `N = 6`，`arr[] = {2, 5, 3, 4, 6}`，`S = "01110"`
> **输出:** `Yes`
> **说明:**
> 可互换的指数为 `{1, 2, 3}`。
> 交换 `arr[1]` 和 `arr[2]` 将数组 `arr[]` 修改为 `{1, 2, 3, 5, 4, 6}`。
> 交换 `arr[3]` 和 `arr[4]` 将数组 `arr[]` 修改为 `{1, 2, 3, 4, 5, 6}`。
>
> **输入:** `N = 6`，`arr[] = {1, 2, 5, 3, 4, 6}`，`S = "01010"`
> **输出:** `No`

**思路:** 看一下数组 `arr[]` 中的某对 `(i, j)`，这样 `i < j` 和初始 `arr[i] > arr[j]`。这意味着所有从 `i` 到 `j - 1` 的互换都应该被允许。然后很容易注意到，只检查 `i` 和 `i + 1` 就足够了，因为任何其他对都可以从中扣除。按照以下步骤解决问题:

*   迭代范围 `[0, N–1]` 并执行以下步骤:
    *   如果 `S[i]` 是 `‘1’`，那么初始化一个变量，说 `j`，等于 `i`。
    *   迭代范围直到 `s[j]` 等于 `‘1’` 且 `j` 小于字符串 `s` 的长度。将 `j` 的值增加 `1`。
    *   将数组中的子数组从 `i` 排序为 `j+1`。
*   迭代范围 `[0, N–2]` 并执行以下步骤:
    *   如果 `arr[i]` 的值大于 `arr[i + 1]`，则打印 `No`，中断循环返回。
*   打印 `Yes`，因为数组是通过交换允许的索引来排序的。

下面是上述方法的实现。

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if it is possible
// to sort the array arr[] by swapping
// array elements from indices containing
// adjacent pairs of 1s in the string s
void checkIfPossibleToSort(int n, int arr[],
                           string s)
{
    // Sort the parts of array
    // where swaps are allowed
    for (int i = 0; i < n - 1; i++) {

        if (s[i] == '1') {
            int j = i;

            // Iterate over the range
            // till s[j] is equal to '1'
            while (s[j] == '1') {
                j++;
            }

            // Sort the subarray
            sort(arr + i, arr + j + 1);

            i = j;
        }
    }

    // Check if the array remains unsorted
    for (int i = 0; i < n - 1; i++) {

        // If found to be true, then it is
        // not possible to sort the array
        if (arr[i] > arr[i + 1]) {
            printf("No\n");
            return;
        }
    }

    printf("Yes\n");
}

// Driver Code
int main()
{
    // Given Input
    int n = 6;
    int arr[] = { 2, 5, 3, 4, 6 };
    string s = "01110";

    // Function Call
    checkIfPossibleToSort(n, arr, s);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.Arrays;

class GFG{

// Function to check if it is possible
// to sort the array arr[] by swapping
// array elements from indices containing
// adjacent pairs of 1s in the string s
public static void checkIfPossibleToSort(int n, int arr[],
                                         String s)
{

    // Sort the parts of array
    // where swaps are allowed
    for(int i = 0; i < n - 1; i++)
    {
        if (s.charAt(i) == '1')
        {
            int j = i;

            // Iterate over the range
            // till s[j] is equal to '1'
            while (s.charAt(j) == '1')
            {
                j++;
            }

            // Sort the subarray
            Arrays.sort(arr, i, j);

            i = j;
        }
    }

    // Check if the array remains unsorted
    for(int i = 0; i < n - 2; i++)
    {

        // If found to be true, then it is
        // not possible to sort the array
        if (arr[i] > arr[i + 1])
        {
            System.out.println("No");
            return;
        }
    }
    System.out.println("Yes");
}

// Driver Code
public static void main(String args[])
{

    // Given Input
    int n = 6;
    int arr[] = { 2, 5, 3, 4, 6 };
    String s = "01110";

    // Function Call
    checkIfPossibleToSort(n, arr, s);
}
}

// This code is contributed by gfgking
```

## Python3

```python
# Python3 program for the above approach

# Function to check if it is possible
# to sort the array arr[] by swapping
# array elements from indices containing
# adjacent pairs of 1s in the string s
def checkIfPossibleToSort(n, arr, s):

   # Sort the parts of array
    # where swaps are allowed
    for i in range(n-1):
        if s[i] == '1':
            j = i

            # Iterate over the range
            # till s[j] is equal to '1'
            while s[j] == '1':
                j += 1

                # sort the array
            arr = arr[:i] + sorted(arr[i:j+1]) + arr[j+1:]
            i = j

     # Check if the array remains unsorted
    for i in range(n-2):

      # If found to be true, then it is
       # not possible to sort the array
        if arr[i] > arr[i+1]:
            print("No")
            return
    print("Yes")

    # Driver code

    # Given input
n = 6
arr = [2, 5, 3, 4, 6]
s = "01110"

# function call
checkIfPossibleToSort(n, arr, s)

# This code is contributed by Parth Manchanda
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if it is possible
// to sort the array arr[] by swapping
// array elements from indices containing
// adjacent pairs of 1s in the string s
public static void checkIfPossibleToSort(int n, int []arr, String s)
{

    // Sort the parts of array
    // where swaps are allowed
    for(int i = 0; i < n - 1; i++)
    {
        if (s[i] == '1')
        {
            int j = i;

            // Iterate over the range
            // till s[j] is equal to '1'
            while (s[j] == '1')
            {
                j++;
            }

            // Sort the subarray
            Array.Sort(arr, i, j);

            i = j;
        }
    }

    // Check if the array remains unsorted
    for(int i = 0; i < n - 2; i++)
    {

        // If found to be true, then it is
        // not possible to sort the array
        if (arr[i] > arr[i + 1])
        {
            Console.Write("No");
            return;
        }
    }
    Console.Write("Yes");
}

// Driver Code
public static void Main(String []args)
{

    // Given Input
    int n = 6;
    int []arr = { 2, 5, 3, 4, 6 };
    String s = "01110";

    // Function Call
    checkIfPossibleToSort(n, arr, s);
}
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```
<script>
// Javascript program for the above approach

// Function to check if it is possible
// to sort the array arr[] by swapping
// array elements from indices containing
// adjacent pairs of 1s in the string s
function checkIfPossibleToSort(n, arr, s) {
  // Sort the parts of array
  // where swaps are allowed
  for (let i = 0; i < n - 1; i++) {
    if (s[i] == "1") {
      let j = i;

      // Iterate over the range
      // till s[j] is equal to '1'
      while (s[j] == "1") {
        j++;
      }

      // Sort the subarray
      arr = [
        ...arr.slice(0, i),
        ...arr.slice(i, j + 1).sort((a, b) => a - b),
        ...arr.slice(j + 1, arr.length - 1),
      ];

      i = j;
    }
  }

  // Check if the array remains unsorted
  for (let i = 0; i < n - 1; i++) {
    // If found to be true, then it is
    // not possible to sort the array
    if (arr[i] > arr[i + 1]) {
      document.write("No<br>");
      return;
    }
  }

  document.write("Yes\n");
}

// Driver Code

// Given Input
let n = 6;
let arr = [2, 5, 3, 4, 6];
let s = "01110";

// Function Call
checkIfPossibleToSort(n, arr, s);

// tHIS CODE IS CONTRIBUTED BY _SAURABH_JAISWAL.
</script>
```

Output:

```
Yes
```

时间复杂度: O(N*log(N))
辅助空间: O(1)