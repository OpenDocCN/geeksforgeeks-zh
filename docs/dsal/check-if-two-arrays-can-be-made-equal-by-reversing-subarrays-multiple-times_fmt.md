# 通过多次反转子阵列检查两个阵列是否可以相等

> 原文: [https://www.geeksforgeeks.org/check-if-two-arrays-can-be-made-equal-by-reversing-subarrays-multiple-times/](https://www.geeksforgeeks.org/check-if-two-arrays-can-be-made-equal-by-reversing-subarrays-multiple-times/)

给定两个阵列 `A[]` 和 `B[]`，任务是通过将 `B` 的子阵列反转任意次数来检查阵列 `B` 是否可以等于 `A`。

**示例:**

> **输入:** `A[] = {1 2 3}`，`B[] = {3 1 2}`
> **输出:** 是
> **解释:**
> 反向子阵在阵列 `B` 中如下所示:
> 反向子阵 `[3，1]`，`B` 变成 `[1，3，2]`
> 反向子阵 `[3，2]`，`B` 变成 `[1，2，3] = A`
> 有多种方式将 `B` 转换为 `A`。
> **输入:**

**逼近:** 由于我们只需要将任意一个子数组反转任意多次就可以使数组 `B` 等于数组 `A`，所以只有当两个数组都是字谜时才有可能。为了检查两个数组是否都是字谜，我们将[对两个数组进行排序](https://www.geeksforgeeks.org/merge-sort/)并检查任何索引元素是否不相同，然后我们将返回 `false`，否则我们将在最后返回 `true`。

以下实施上述方法:

## C++

```cpp
// C++ implementation to check if
// two arrays can be made equal

#include <bits/stdc++.h>
using namespace std;

// Function to check if array B
// can be made equal to array A
bool canMadeEqual(int A[],
                  int B[], int n)
{
    // sort both the arrays
    sort(A, A + n);
    sort(B, B + n);

    // Check if both the arrays
    // are equal or not
    for (int i = 0; i < n; i++)
        if (A[i] != B[i])
            return false;
    return true;
}

// Driver Code
int main()
{
    int A[] = { 1, 2, 3 };
    int B[] = { 1, 3, 2 };
    int n = sizeof(A) / sizeof(A[0]);
    if (canMadeEqual(A, B, n))
        cout << "Yes";
    else
        cout << "No";

    return 0;
}
```

## C

```c
// C implementation to check if
// two arrays can be made equal
#include<stdio.h>
#include<math.h>

int sort(int a[],int n)
{
    int i, j, tmp;
    for(i = 0; i < n; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(a[j] <a[i])
            {
                tmp = a[i];
                a[i] = a[j];
                a[j] = tmp;
            }
        }
    }
    return 0;
}

// Function to check if array B
// can be made equal to array A
int canMadeEqual(int A[], int B[], int n)
{
    int i;

    // Sort both arrays
    sort(A, n);
    sort(B, n);

    // Check both arrays equal or not
    for(i = 0; i < n; i++)
    {
        if (A[i] != B[i])
        {
            return(0);
        }
    }
    return (1);
}

// Driver Code
int main()
{
    int A[] = { 1, 2, 3 };
    int n;
    int B[] = { 1, 3, 2 };

    n = sizeof(A) / sizeof(A[0]);
    if(canMadeEqual(A, B, n))
    {
        printf("Yes");
    }
    else
    {
        printf("No");
    }
    return 0;
}

// This code is contributed by adityakumar27200
```

## Java

```java
// Java implementation to check if
// two arrays can be made equal
import java.util.*;

class GFG{

// Function to check if array B
// can be made equal to array A
public static boolean canMadeEqual(int[] A,
                                   int[] B,
                                   int n)
{

    // Sort both the arrays
    Arrays.sort(A);
    Arrays.sort(B);

    // Check if both the arrays
    // are equal or not
    for(int i = 0; i < n; i++)
    {
        if (A[i] != B[i])
        {
            return false;
        }
    }
    return true;
}

// Driver code
public static void main(String[] args)
{
    int A[] = { 1, 2, 3 };
    int B[] = { 1, 3, 2 };
    int n = A.length;

    if (canMadeEqual(A, B, n))
        System.out.print("Yes");
    else
        System.out.print("No");
}
}

// This code is contributed by divyeshrabadiya07
```

## Python 3

```python
# Python3 implementation to check if
# two arrays can be made equal

# Function to check if array B
# can be made equal to array A
def canMadeEqual(A, B, n):

  # Sort both the arrays
  A.sort()
  B.sort()

  # Check if both the arrays
  # are equal or not
  for i in range(n):
    if (A[i] != B[i]):
      return False

  return True

# Driver Code
if __name__ == "__main__":

  A = [ 1, 2, 3 ]
  B = [ 1, 3, 2 ]
  n = len(A)

  if (canMadeEqual(A, B, n)):
    print( "Yes")
  else:
    print("No")

# This code is contributed by chitranayal
```

## C#

```csharp
// C# implementation to check if
// two arrays can be made equal
using System;

class GFG{

// Function to check if array B
// can be made equal to array A
static bool canMadeEqual(int[] A,
                         int[] B,
                         int n)
{

    // Sort both the arrays
    Array.Sort(A);
    Array.Sort(B);

    // Check if both the arrays
    // are equal or not
    for(int i = 0; i < n; i++)
    {
        if (A[i] != B[i])
        {
            return false;
        }
    }
    return true;
}

// Driver code
public static void Main()
{
    int[] A = { 1, 2, 3 };
    int[] B = { 1, 3, 2 };
    int n = A.Length;

    if (canMadeEqual(A, B, n))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}

// This code is contributed by adityakumar27200
```

## JavaScript

```javascript
<script>

// Javascript implementation to check if
// two arrays can be made equal

// Function to check if array B
// can be made equal to array A
function canMadeEqual(A, B, n)
{
    // sort both the arrays
    A.sort();
    B.sort();

    // Check if both the arrays
    // are equal or not
    for (var i = 0; i < n; i++)
        if (A[i] != B[i])
            return false;
    return true;
}

// Driver Code
var A = [ 1, 2, 3 ];
var B = [ 1, 3, 2 ];
var n = A.length;
if (canMadeEqual(A, B, n))
    document.write( "Yes");
else
    document.write("No");

// This code is contributed by rutvik_56.
</script>
```

**Output**

```
Yes
```

**时间复杂度:** `O(N * Log N)`
**辅助空间:** `O(1)`