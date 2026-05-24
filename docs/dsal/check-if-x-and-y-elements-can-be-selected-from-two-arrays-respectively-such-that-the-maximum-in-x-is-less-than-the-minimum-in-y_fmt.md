# 检查是否可以分别从两个数组中选择 X 和 Y 元素，使得 X 中的最大值小于 Y 中的最小值

> 原文: [https://www.geeksforgeeks.org/check-if-x-and-y-elements-can-be-selected-from-two-arrays-respectively-such-that-the-maximum-in-x-is-less-than-the-minimum-in-y/](https://www.geeksforgeeks.org/check-if-x-and-y-elements-can-be-selected-from-two-arrays-respectively-such-that-the-maximum-in-x-is-less-than-the-minimum-in-y/)

给定两个分别由 **N** 和 **M** 整数组成的数组 `arr1[]` 和 `arr2[]` 以及两个整数 **X** 和 **Y**，任务是检查是否有可能从 `arr1[]` 中选择 **X** 元素，从 `arr2[]` 中选择 **Y** 元素，使得 `arr1[]` 中选择的 **X** 个元素中的最大值小于 `arr2[]` 中选择的 **Y** 个元素中的最小值。如果可能，则打印 **“是”**。否则，打印 **“否”**。

**示例:**

> **输入:** `arr1[] = {1，1，1，1，1}`，`arr2[] = {2，2}`，`X = 3`，`Y = 1`
> **输出:** 是
> **解释:** 每个可能的选择都满足上述条件，因为 `arr1[]` 的每个元素都小于 `arr2[]` 中的最小元素。
>
> **输入:** `arr1[] = {1，2，3}`，`arr2[] = {3，4，5}`，`X = 2`，`Y = 1`
> **输出:** 是
> **解释:** 一种可能的选择是从 `arr1[]` 中取索引 0 和 1 处的元素，从 `arr2[]` 中取索引 0 处的元素，即 `{1，2}` 和 `{3}`。

**方法:** 思路是将两个数组按照升序排序，然后从 `arr1[]` 中选择第一个 **X** 元素，从 `arr2[]` 中选择最后一个 **Y** 元素。按照以下步骤解决问题:

*   按升序排列两个数组。
*   如果 **X** 大于 **N** 或 **Y** 大于 **M**，则打印 **“否”**，因为无法选择任何此类组合。
*   否则，如果 `arr1[X-1]` 的值小于 `arr2[M-Y]`，则打印 **“是”**。
*   否则，打印 **“否”**。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if it is possible to
// choose X and Y elements from a[] and
// b[] such that maximum element among
// X element is less than minimum
// element among Y elements
string check(int a[], int b[], int Na,
             int Nb, int k, int m)
{
    // Check if there are atleast X
    // elements in arr1[] and atleast
    // Y elements in arr2[]
    if (Na < k || Nb < m)
        return "No";

    // Sort arrays in ascending order
    sort(a, a + Na);
    sort(b, b + Nb);

    // Check if (X - 1)-th element in arr1[]
    // is less than from M-Yth element
    // in arr2[]
    if (a[k - 1] < b[Nb - m]) {
        return "Yes";
    }

    // Return false
    return "No";
}

// Driver Code
int main()
{
    int arr1[] = { 1, 2, 3 };
    int arr2[] = { 3, 4, 5 };
    int N = sizeof(arr1) / sizeof(arr1[0]);
    int M = sizeof(arr2) / sizeof(arr2[0]);

    int X = 2, Y = 1;

    // Function Call
    cout << check(arr1, arr2, N, M, X, Y);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
import java.util.*;

class GFG{

// Function to check if it is possible to
// choose X and Y elements from a[] and
// b[] such that maximum element among
// X element is less than minimum
// element among Y elements
static String check(int[] a, int[] b,
                    int Na, int Nb,
                    int k, int m)
{

    // Check if there are atleast X
    // elements in arr1[] and atleast
    // Y elements in arr2[]
    if (Na < k || Nb < m)
        return "No";

    // Sort arrays in ascending order
    Arrays.sort(a);
    Arrays.sort(b);

    // Check if (X - 1)-th element in arr1[]
    // is less than from M-Yth element
    // in arr2[]
    if (a[k - 1] < b[Nb - m])
    {
        return "Yes";
    }

    // Return false
    return "No";
}

// Driver Code
public static void main(String[] args)
{
    int[] arr1 = { 1, 2, 3 };
    int[] arr2 = { 3, 4, 5 };
    int N = arr1.length;
    int M = arr2.length;

    int X = 2, Y = 1;

    // Function Call
    System.out.println(check(
        arr1, arr2, N, M, X, Y));
}
}

// This code is contributed by Dharanendra L V
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if it is possible to
# choose X and Y elements from a[] and
# b[] such that maximum element among
# X element is less than minimum
# element among Y elements
def check( a, b, Na, Nb, k, m):

  # Check if there are atleast X
  # elements in arr1[] and atleast
  # Y elements in arr2[]
  if (Na < k or Nb < m):
    return "No"

  # Sort arrays in ascending order
  a.sort()
  b.sort()

  # Check if (X - 1)-th element in arr1[]
  # is less than from M-Yth element
  # in arr2[]
  if (a[k - 1] < b[Nb - m]):
    return "Yes"

  # Return false
  return "No"

# Driver Code
arr1 = [ 1, 2, 3 ]
arr2 = [ 3, 4, 5 ]
N = len(arr1)
M = len(arr2)
X = 2
Y = 1

# Function Call
print(check(arr1, arr2, N, M, X, Y))

# This code is contributed by rohitsongh07052.
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if it is possible to
// choose X and Y elements from a[] and
// b[] such that maximum element among
// X element is less than minimum
// element among Y elements
static string check(int[] a, int[] b,
                    int Na, int Nb,
                    int k, int m)
{

    // Check if there are atleast X
    // elements in arr1[] and atleast
    // Y elements in arr2[]
    if (Na < k || Nb < m)
        return "No";

    // Sort arrays in ascending order
    Array.Sort(a);
    Array.Sort(b);

    // Check if (X - 1)-th element in arr1[]
    // is less than from M-Yth element
    // in arr2[]
    if (a[k - 1] < b[Nb - m])
    {
        return "Yes";
    }

    // Return false
    return "No";
}

// Driver Code
static public void Main()
{
    int[] arr1 = { 1, 2, 3 };
    int[] arr2 = { 3, 4, 5 };
    int N = arr1.Length;
    int M = arr2.Length;

    int X = 2, Y = 1;

    // Function Call
    Console.WriteLine(check(
        arr1, arr2, N, M, X, Y));
}
}

// This code is contributed by Dharanendra L V
```

## JavaScript

```javascript
<script>
// javascript program for the above approach
// Function to check if it is possible to
// choose X and Y elements from a and
// b such that maximum element among
// X element is less than minimum
// element among Y elements
function check(a, b, Na, Nb, k, m)
{

    // Check if there are atleast X
    // elements in arr1 and atleast
    // Y elements in arr2
    if (Na < k || Nb < m)
        return "No";

    // Sort arrays in ascending order
    a.sort();
    b.sort();

    // Check if (X - 1)-th element in arr1
    // is less than from M-Yth element
    // in arr2
    if (a[k - 1] < b[Nb - m]) {
        return "Yes";
    }

    // Return false
    return "No";
}

// Driver Code
var arr1 = [ 1, 2, 3 ];
var arr2 = [ 3, 4, 5 ];
var N = arr1.length;
var M = arr2.length;

var X = 2, Y = 1;

// Function Call
document.write(check(arr1, arr2, N, M, X, Y));

// This code is contributed by todaysgaurav
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** `O(N * log N)`
**辅助空间:** `O(1)`