# 数组右旋转 K 次后的第 m 个元素

> 原文：[https://www.geeksforgeeks.org/mth-element-after-k-right-rotations-of-an-array/](https://www.geeksforgeeks.org/mth-element-after-k-right-rotations-of-an-array/)

给定非负整数 `K`、`M` 和由 `N` 个元素组成的数组 `arr[]`，任务是在 `K` 次右旋转后找到数组的第 `M` 个元素。

## 示例

> **输入:** `arr[] = {3, 4, 5, 23}`，`K = 2`，`M = 1`
> **输出:** `5`
> **解释:**
> 第一次右旋转后的数组 `a1[] = {23, 3, 4, 5}`
> 第二次右旋转后的数组 `a2[] = {5, 23, 3, 4}`
> 第一个元素在 2 次右旋转后为 5。
> **输入:** `arr[] = {1, 2, 3, 4, 5}`，`K = 3`，`M = 2`
> **输出:** `4`
> **解释:**
> 右旋转 3 圈后的数组第二个位置有 4。

## 天真法

解决问题最简单的方法就是[执行右旋转](https://www.geeksforgeeks.org/left-rotation-right-rotation-string-2/)操作 `K` 次，然后找到最终数组的第 `M` 个元素。
**时间复杂度:** `O(N * K)`
**辅助空间:** `O(N)`

## 高效方法

要优化问题，需要进行以下观察：

*   如果数组旋转 `N` 次，它将再次返回初始数组。

> 例如，`a[] = {1, 2, 3, 4, 5}`，`K=5`
> 右旋转 5 次后修改数组 `a5[] = {1, 2, 3, 4, 5}`。

*   因此，`K` 次旋转后数组中的元素与原数组中索引 `K % N` 处的元素相同。
*   如果 `K >= M`，则 `K` 次右旋转后数组的第 `M` 个元素为

> 原数组中的第 `{ (N-K) + (M-1) }` 个元素。

*   如果 `K < M`，`K` 次右旋转后数组的第 `M` 个元素为:

> 原数组中的第 `(M–K–1)` 个元素。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach
#include<bits/stdc++.h>
using namespace std;

// Function to return Mth element of
// array after k right rotations
int getFirstElement(int a[], int N,
                    int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;
    int index;

    // If K is greater or equal to M
    if (K >= M)

        // Mth element after k right
        // rotations is (N-K)+(M-1) th
        // element of the array
        index = (N - K) + (M - 1);

    // Otherwise
    else

        // (M - K - 1) th element
        // of the array
        index = (M - K - 1);

    int result = a[index];

    // Return the result
    return result;
}

// Driver Code
int main()
{
    int a[] = { 1, 2, 3, 4, 5 };

    int N = sizeof(a) / sizeof(a[0]);

    int K = 3, M = 2;

    cout << getFirstElement(a, N, K, M);

    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
class GFG{

// Function to return Mth element of
// array after k right rotations
static int getFirstElement(int a[], int N,
                           int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;
    int index;

    // If K is greater or equal to M
    if (K >= M)

        // Mth element after k right
        // rotations is (N-K)+(M-1) th
        // element of the array
        index = (N - K) + (M - 1);

    // Otherwise
    else

        // (M - K - 1) th element
        // of the array
        index = (M - K - 1);

    int result = a[index];

    // Return the result
    return result;
}

// Driver Code
public static void main(String[] args)
{
    int a[] = { 1, 2, 3, 4, 5 };

    int N = 5;

    int K = 3, M = 2;

    System.out.println(getFirstElement(a, N, K, M));
}
}

// This code is contributed by Ritik Bansal
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to return Mth element of
# array after k right rotations
def getFirstElement(a, N, K, M):

    # The array comes to original state
    # after N rotations
    K %= N

    # If K is greater or equal to M
    if (K >= M):

        # Mth element after k right
        # rotations is (N-K)+(M-1) th
        # element of the array
        index = (N - K) + (M - 1)

    # Otherwise
    else:

        # (M - K - 1) th element
        # of the array
        index = (M - K - 1)

    result = a[index]

    # Return the result
    return result

# Driver Code
if __name__ == "__main__":

    a = [ 1, 2, 3, 4, 5 ]
    N = len(a)

    K , M = 3, 2

    print( getFirstElement(a, N, K, M))

# This code is contributed by chitranayal
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG{

// Function to return Mth element of
// array after k right rotations
static int getFirstElement(int []a, int N,
                        int K, int M)
{
    // The array comes to original state
    // after N rotations
    K %= N;
    int index;

    // If K is greater or equal to M
    if (K >= M)

        // Mth element after k right
        // rotations is (N-K)+(M-1) th
        // element of the array
        index = (N - K) + (M - 1);

    // Otherwise
    else

        // (M - K - 1) th element
        // of the array
        index = (M - K - 1);

    int result = a[index];

    // Return the result
    return result;
}

// Driver Code
public static void Main()
{
    int []a = { 1, 2, 3, 4, 5 };

    int N = 5;

    int K = 3, M = 2;

    Console.Write(getFirstElement(a, N, K, M));
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>
// JavaScript program to implement
// the approach

// Function to return Mth element of
// array after k right rotations
function getFirstElement(a, N,
                           K, M)
{
    // The array comes to original state
    // after N rotations
    K %= N;
    let index;

    // If K is greater or equal to M
    if (K >= M)

        // Mth element after k right
        // rotations is (N-K)+(M-1) th
        // element of the array
        index = (N - K) + (M - 1);

    // Otherwise
    else

        // (M - K - 1) th element
        // of the array
        index = (M - K - 1);

    let result = a[index];

    // Return the result
    return result;
}

// Driver Code   

    let a = [ 1, 2, 3, 4, 5 ];

    let N = 5;

    let K = 3, M = 2;

    document.write(getFirstElement(a, N, K, M));

</script>
```

**输出:**

```
4
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`