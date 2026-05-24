# 在左旋转 K 次后找到数组的第 m 个元素

> 原文：[https://www.geeksforgeeks.org/find-the-mth-element-of-the-array-after-k-left-rotations/](https://www.geeksforgeeks.org/find-the-mth-element-of-the-array-after-k-left-rotations/)

给定非负整数 `K`、`M` 和带有 `N` 元素的数组 `arr[]`，在 `K` 次左旋转后找到数组的第 `M` 个元素。

**示例：**

> **输入：** `arr[] = {3, 4, 5, 23}`，`K = 2`，`M = 1`
> **输出：** `5`
> **解释：**
> 第一次左旋转后的数组 `a1[] = {4, 5, 23, 3}`
> 第二次左旋转后的数组 `a2[] = {5, 23, 3, 4}`
> 左旋转 2 次后第 1 个元素为 `5`。

> **输入：** `arr[] = {1, 2, 3, 4, 5}`，`K = 3`，`M = 2`
> **输出：** `5`
> **说明：**
> 左旋转 3 圈后的数组第二个位置有 `5`。

### 天真法

思路是[执行左旋转](https://www.geeksforgeeks.org/print-left-rotation-array/)操作 `K` 次，然后找到最终数组的第 `M` 个元素。

**时间复杂度：** `O(N * K)`
**辅助空间：** `O(N)`

### 高效方法

要优化问题，请注意以下几点：

1.  如果数组被旋转 `N` 次，它会再次返回初始数组。
    > 例如，`a[] = {1, 2, 3, 4, 5}`，`K=5`，那么数组经过 5 次左旋转 `a5[] = {1, 2, 3, 4, 5}`。

因此，`K` 次旋转后数组中的元素与原数组中索引 `K % N` 处的元素相同。

2.  `K` 次左旋转后数组的第 `M` 个元素是原数组的第 `{(K + M – 1) % N}` 个元素。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return Mth element of
// array after k left rotations
int getFirstElement(int a[], int N, int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;

    // Mth element after k left rotations
    // is (K+M-1)%N th element of the
    // original array
    int index = (K + M - 1) % N;

    int result = a[index];

    // Return the result
    return result;
}

// Driver Code
int main()
{
    // Array initialization
    int a[] = { 3, 4, 5, 23 };

    // Size of the array
    int N = sizeof(a) / sizeof(a[0]);

    // Given K rotation and Mth element
    // to be found after K rotation
    int K = 2, M = 1;

    // Function call
    cout << getFirstElement(a, N, K, M);
    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;
class GFG{

// Function to return Mth element of
// array after k left rotations
public static int getFirstElement(int[] a, int N,
                                  int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;

    // Mth element after k left rotations
    // is (K+M-1)%N th element of the
    // original array
    int index = (K + M - 1) % N;

    int result = a[index];

    // Return the result
    return result;
}

// Driver code
public static void main(String[] args)
{
    // Array initialization
    int a[] = { 3, 4, 5, 23 };

    // Size of the array
    int N = a.length;

    // Given K rotation and Mth element
    // to be found after K rotation
    int K = 2, M = 1;

    // Function call
    System.out.println(getFirstElement(a, N, K, M));
}
}

// This code is contributed by divyeshrabadiya07
```

## Python3

```python
# Python3 program for the above approach

# Function to return Mth element of
# array after k left rotations
def getFirstElement(a, N, K, M):

    # The array comes to original state
    # after N rotations
    K %= N

    # Mth element after k left rotations
    # is (K+M-1)%N th element of the
    # original array
    index = (K + M - 1) % N

    result = a[index]

    # Return the result
    return result

# Driver Code
if __name__ == '__main__':

    # Array initialization
    a = [ 3, 4, 5, 23 ]

    # Size of the array
    N = len(a)

    # Given K rotation and Mth element
    # to be found after K rotation
    K = 2
    M = 1

    # Function call
    print(getFirstElement(a, N, K, M))

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to return Mth element of
// array after k left rotations
public static int getFirstElement(int[] a, int N,
                                  int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;

    // Mth element after k left rotations
    // is (K+M-1)%N th element of the
    // original array
    int index = (K + M - 1) % N;

    int result = a[index];

    // Return the result
    return result;
}

// Driver code
public static void Main(string[] args)
{
    // Array initialization
    int []a = { 3, 4, 5, 23 };

    // Size of the array
    int N = a.Length;

    // Given K rotation and Mth element
    // to be found after K rotation
    int K = 2, M = 1;

    // Function call
    Console.Write(getFirstElement(a, N, K, M));
}
}

// This code is contributed by rutvik_56
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to return Mth element of
// array after k left rotations
function getFirstElement(a, N, K, M) {

    // The array comes to original state
    // after N rotations
    K %= N;

    // Mth element after k left rotations
    // is (K+M-1)%N th element of the
    // original array
    var index = (K + M - 1) % N;

    var result = a[index];

    // Return the result
    return result;
}

// Driver code

// Array initialization
var a = [ 3, 4, 5, 23 ];

// Size of the array
var N = a.length;

// Given K rotation and Mth element
// to be found after K rotation
var K = 2, M = 1;

// Function call
document.write(getFirstElement(a, N, K, M));

// This code contributed by gauravrajput1
</script>
```

**输出：**

```
5
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`