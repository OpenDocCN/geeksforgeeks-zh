# 给定数组中偶数索引处的偶数元素之和与奇数索引处的奇数元素之和之间的绝对差

## 问题描述
给定一个包含 `N` 个元素的数组 `arr[]`，任务是找到偶数索引处的偶数元素的和与奇数索引处的奇数元素的和之间的**绝对差**。考虑基于 1 的索引。

## 示例
**输入:** `arr[] = {3, 4, 1, 5}`
**输出:** 0
**解释:**
偶数索引偶数元素之和: 4 `{4}`
奇数索引奇数元素之和: 4 `{3, 1}`
绝对差 = 4 - 4 = 0

**输入:** `arr[] = {4, 2, 1, 3}`
**输出:** 1

## 方法
该任务可以通过从左到右遍历数组来解决，分别跟踪奇数和偶数索引处的奇数和偶数元素的和。按照以下步骤解决问题:
1.  从左到右遍历数组。
2.  如果当前索引为**偶数**，则检查该索引处的元素是否为偶数，如果为偶数，则将其加到**偶数**之和。
3.  如果当前索引为**奇数**，检查该索引处的元素是否为奇数，如果为奇数，将其加到**奇数**之和。
4.  返回奇数和与偶数和之间的**绝对差**。

下面是上述方法的实现。

## C++
```cpp
// C++ program to implement the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the required absolute difference
int xorOr(int arr[], int N)
{
    // Store the count of odds & evens at odd
    // and even indices respectively
    int evens = 0, odds = 0;

    // Traverse the array to count even/odd
    for (int i = 0; i < N; i++) {
        if ((i + 1) % 2 == 0
            && arr[i] % 2 == 0)
            evens += arr[i];
        else if ((i + 1) % 2 != 0
                 && arr[i] % 2 != 0)
            odds += arr[i];
    }

    return abs(odds - evens);
}

// Driver Code
int main()
{
    int arr[] = { 3, 4, 1, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << xorOr(arr, N);
    return 0;
}
```

## Java
```java
// Java code for the above approach
import java.util.*;
class GFG
{

// Function to find the required absolute difference
static int xorOr(int arr[], int N)
{
    // Store the count of odds & evens at odd
    // and even indices respectively
    int evens = 0, odds = 0;

    // Traverse the array to count even/odd
    for (int i = 0; i < N; i++) {
        if ((i + 1) % 2 == 0
            && arr[i] % 2 == 0)
            evens += arr[i];
        else if ((i + 1) % 2 != 0
                 && arr[i] % 2 != 0)
            odds += arr[i];
    }

    return Math.abs(odds - evens);
}

// Driver Code
    public static void main (String[] args) {
       int arr[] = { 3, 4, 1, 5 };
    int N = arr.length;

        System.out.println(xorOr(arr, N));
    }
}

// This code is contributed by Potta Lokesh
```

## Python 3
```python
# Python code for the above approach

# Function to find the required absolute difference
def xorOr(arr, N):

    # Store the count of odds & evens at odd
    # and even indices respectively
    evens = 0;
    odds = 0;

    # Traverse the array to count even/odd
    for i in range(N):
        if ((i + 1) % 2 == 0 and arr[i] % 2 == 0):
            evens += arr[i];
        elif ((i + 1) % 2 != 0 and arr[i] % 2 != 0):
            odds += arr[i];

    return abs(odds - evens);

# Driver Code
if __name__ == '__main__':
    arr = [3, 4, 1, 5];
    N = len(arr);

    print(xorOr(arr, N));

# This code is contributed by 29AjayKumar
```

## C#
```csharp
// C# code for the above approach
using System;
using System.Collections;
class GFG
{

// Function to find the required absolute difference
static int xorOr(int []arr, int N)
{

    // Store the count of odds & evens at odd
    // and even indices respectively
    int evens = 0, odds = 0;

    // Traverse the array to count even/odd
    for (int i = 0; i < N; i++) {
        if ((i + 1) % 2 == 0
            && arr[i] % 2 == 0)
            evens += arr[i];
        else if ((i + 1) % 2 != 0
                 && arr[i] % 2 != 0)
            odds += arr[i];
    }

    return Math.Abs(odds - evens);
}

// Driver Code
public static void Main () {
    int []arr = { 3, 4, 1, 5 };
    int N = arr.Length;

        Console.Write(xorOr(arr, N));
}
}

// This code is contributed by Samim Hossain Mondal.
```

## JavaScript
```javascript
<script>
// Javascript program to implement the above approach

// Function to find the required absolute difference
function xorOr(arr, N) {
    // Store the count of odds & evens at odd
    // and even indices respectively
    let evens = 0, odds = 0;

    // Traverse the array to count even/odd
    for (let i = 0; i < N; i++) {
        if ((i + 1) % 2 == 0
            && arr[i] % 2 == 0)
            evens += arr[i];
        else if ((i + 1) % 2 != 0
            && arr[i] % 2 != 0)
            odds += arr[i];
    }

    return Math.abs(odds - evens);
}

// Driver Code
let arr = [3, 4, 1, 5];
let N = arr.length;
document.write(xorOr(arr, N));

// This code is contributed by gfgking.
</script>
```

**输出**
```
0
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`