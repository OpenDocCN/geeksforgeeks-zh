# 通过重新排列数组中的元素来检查一个数组是否可以适合另一个数组

> 原文：[https://www.geeksforgeeks.org/check-whether-an-array-can-be-fit-into-another-array-rearranging-the-elements-in-the-array/](https://www.geeksforgeeks.org/check-whether-an-array-can-be-fit-into-another-array-rearranging-the-elements-in-the-array/)

给定两个大小相同的数组 `A` 和 `B`，大小为 `n`。检查数组 `A` 是否可以放入数组 `B`。如果通过排列两个数组的元素，存在第一个数组的第 `i` 个元素小于或等于第二个数组的第 `i` 个元素的解，则称一个数组可以放入另一个数组。

## 示例

```
Input : A[] = { 7, 5, 3, 2 }, B[] = { 5, 4, 8, 7 }
Output : YES 
Rearrange the first array to {3, 2, 7, 5} 
Do not rearrange the second array's element. 
After rearranging, all Ai<=Bi. 

Input : A[] = { 7, 5, 3, 2, 5, 105, 45, 10 }, B[] = { 2, 4, 0, 5, 6, 9, 75, 84 }
Output : NO
```

## 方法

对两个数组进行排序，检查 `A[i]` 是否小于或等于 `B[i]`，对于所有 `0 ≤ i ≤ N`。如果在任意第 `i` 个位置 `A[i]` 大于 `B[i]`，返回 `false`，否则返回 `true`。

以下是上述方法的实现：

### C++

```cpp
// C++ Program to check whether an array
// can be fit into another array with given
// condition.
#include <bits/stdc++.h>
using namespace std;

// Returns true if the array A can be fit into
// array B, otherwise false
bool checkFittingArrays(int A[], int B[], int N)
{
    // Sort both the arrays
    sort(A, A + N);
    sort(B, B + N);

    // Iterate over the loop and check whether every
    // array element of A is less than or equal to
    // its corresponding array element of B
    for (int i = 0; i < N; i++)
        if (A[i] > B[i])
            return false;

    return true;
}

// Driver Code
int main()
{
    int A[] = { 7, 5, 3, 2 };
    int B[] = { 5, 4, 8, 7 };
    int N = sizeof(A) / sizeof(A[0]);

    if (checkFittingArrays(A, B, N))
        cout << "YES";
    else
        cout << "NO";
    return 0;
}
```

### Java

```java
// Java Program to check
// whether an array can
// be fit into another
// array with given
// condition.
import java.io.*;
import java.util.*;
import java.lang.*;

class GFG
{

// Returns true if the
// array A can be fit
// into array B,
// otherwise false
static boolean checkFittingArrays(int []A,
                                  int []B,
                                  int N)
{

    // Sort both the arrays
    Arrays.sort(A);
    Arrays.sort(B);

    // Iterate over the loop
    // and check whether every
    // array element of A is
    // less than or equal to
    // its corresponding array
    // element of B
    for (int i = 0; i < N; i++)
        if (A[i] > B[i])
            return false;

    return true;
}

// Driver Code
public static void main(String[] args)
{
    int A[] = {7, 5, 3, 2};
    int B[] = {5, 4, 8, 7};
    int N = A.length;

    if (checkFittingArrays(A, B, N))
        System.out.print("YES");
    else
        System.out.print("NO");
}
}
```

### Python 3

```python
# Python3 Program to check whether an array
# can be fit into another array with given
# condition.

# Returns true if the array A can be fit into
# array B, otherwise false
def checkFittingArrays(A, B, N):

    # Sort both the arrays
    A = sorted(A)
    B = sorted(B)

    # Iterate over the loop and check whether
    # every array element of A is less than
    # or equal to its corresponding array
    # element of B
    for i in range(N):
        if (A[i] > B[i]):
            return False

    return True

# Driver Code
A = [7, 5, 3, 2]
B = [5, 4, 8, 7]
N = len(A)

if (checkFittingArrays(A, B, N)):
    print("YES")
else:
    print("NO")

# This code is contributed
# by mohit kumar
```

### C#

```csharp
// C# Program to check
// whether an array can
// be fit into another
// array with given
// condition.
using System;

class GFG
{

// Returns true if the
// array A can be fit
// into array B,
// otherwise false
static bool checkFittingArrays(int []A,
                               int []B,
                               int N)
{

    // Sort both the arrays
    Array.Sort(A);
    Array.Sort(B);

    // Iterate over the loop
    // and check whether every
    // array element of A is
    // less than or equal to
    // its corresponding array
    // element of B
    for (int i = 0; i < N; i++)
        if (A[i] > B[i])
            return false;

    return true;
}

// Driver Code
public static void Main ()
{
    int []A = {7, 5, 3, 2};
    int []B = {5, 4, 8, 7};
    int N = A.Length;

    if (checkFittingArrays(A, B, N))
        Console.WriteLine("YES");
    else
        Console.WriteLine("NO");
}
}

// This code is contributed
// by anuj_67.
```

### PHP

```php
<?php
// PHP Program to check whether an
// array can be fit into another
// array with given condition.
// Returns true if the array A can
// be fit into array B, otherwise false
function checkFittingArrays($A, $B, $N)
{
    // Sort both the arrays
    sort($A);
    sort($B);

    // Iterate over the loop and check
    // whether every array element of
    // A is less than or equal to its
    // corresponding array element of B
    for ($i = 0; $i < $N; $i++)
        if ($A[$i] > $B[$i])
            return false;

    return true;
}

// Driver Code
$A = array( 7, 5, 3, 2 );
$B = array( 5, 4, 8, 7 );
$N = count($A);

if (checkFittingArrays($A, $B, $N))
    echo "YES";
else
    echo "NO";

// This code is contributed by shs
?>
```

### JavaScript

```javascript
<script>
// Javascript Program to check
// whether an array can
// be fit into another
// array with given
// condition.

    // Returns true if the
    // array A can be fit
    // into array B,
    // otherwise false
    function checkFittingArrays(A, B, N)
    {

        // Sort both the arrays
    A.sort(function(a, b){return a - b;});
    B.sort(function(a, b){return a - b;});

    // Iterate over the loop
    // and check whether every
    // array element of A is
    // less than or equal to
    // its corresponding array
    // element of B
    for (let i = 0; i < N; i++)
        if (A[i] > B[i])
            return false;

    return true;
    }

    // Driver Code
    let A = [7, 5, 3, 2];
    let B = [5, 4, 8, 7];
    let N = A.length;
    if (checkFittingArrays(A, B, N))
        document.write("YES");
    else
        document.write("NO");

// This code is contributed by unknown2108
</script>
```

**输出：**

```
YES
```

**时间复杂度**：`O(N * logN)`，其中 `N` 为数组的大小。