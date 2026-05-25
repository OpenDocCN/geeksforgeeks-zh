# 将 2n 个整数混洗为 a1-b1-a2-b2-a3-b3-..bn 不使用额外空间 | 第 2 集

> 原文: [https://www.geeksforgeeks.org/shuffle-2n-integers-as-a1-b1-a2-b2-a3-b3-bn-without-using-extra-space-set-2/](https://www.geeksforgeeks.org/shuffle-2n-integers-as-a1-b1-a2-b2-a3-b3-bn-without-using-extra-space-set-2/)

## 问题描述

给定一个由 `2*N` 元素组成的数组 `arr[]`，其形式为 `{ a1, a2, …, aN, b1, b2, …, bN }`，任务是将数组洗牌至 `{a1, b1, a2, b2, a3, b3, …, an, bn}` 的格式。

## 示例

> **输入:** `arr[] = { 1, 3, 5, 2, 4, 6 }`
> **输出:** `1 2 3 4 5 6`
> **解释:**
> 输出包含 `{ a1, b1, a2, b2, a3, b3 }`。
>
> **输入:** `arr[] = {1, 2, 3, -1, -2, -3}`
> **输出:** `1 -1 2 -2 3 -3`

## 分治方法

如果一个数组的大小是 2 的次方，那么就按照文章“使用分治技巧，以 `{a1, b1, a2, b2, a3, b3, …, an, bn}` 的格式洗牌 2n 个整数”的方法处理。
**时间复杂度:** `O(N * log(N))`
**辅助空间:** `O(1)`

## 替代方法

上述方法将通过递归划分数组，使两半长度相等，从而适用于 `N` 的所有可能值。按照以下步骤解决问题：

*   定义一个递归函数，比如 `shuffle(start, end)`。
    *   如果数组长度能被 4 整除，那么计算数组的中点，比如 `mid = start+(end–start+1)/2`。
    *   否则，`mid = start+(end–start+1)/2–1`。
    *   计算两个子数组的中点，比如 `mid1 = start+(mid–start)/2`，`mid2 = mid+(end–mid+1)/2`。
    *   在范围 `[mid1, mid2-1]`，`[mid1, mid-1]` 和 `[mid, mid2-1]` 内反转子数组。
    *   递归调用子数组 `[start, mid-1]` 和 `[mid, end]`，即 `shuffle(start, mid-1)` 和 `shuffle(mid, end)`。
*   最后打印数组。

### 插图

考虑一个数组 `arr[] = {a1, a2, a3, b1, b2, b3}`：

1.  将数组分成两半，两部分长度相等，即 `a1, a2` : `a3, b1, b2, b3`。
2.  将前半部分的中间反转到后半部分的中间，即 `a1, b1` : `a3, a2, b2, b3`。
3.  现在，将前半部分的中间反转为子数组 `[0, 5]`，`a1, b1` : `a3, a2, b2, b3` 的中间。
4.  现在将子数组 `[0, 5]` 的中间反转到后半部分的中间，`a1, b1` : `a2, a3, b2, b3`。
5.  递归调用数组 `{a1, b1}` 和 `{a2, a3, b2, b3}`。
6.  应用上述操作后，现在数组 `{a2, a3, b2, b3}` 修改为 `{a2, b2, a3, b3}`。
7.  现在 `arr[]` 修改为 `{a1, b1, a2, b2, a3, b3}`。

## 代码实现

下面是上述方法的实现：

### C

```c
// C program for the above approach
#include <stdio.h>

// Function to reverse the array from the
// position 'start' to position 'end'
void reverse(int arr[], int start, int end)
{

    // Stores mid of start and end
    int mid = (end - start + 1) / 2;

    // Traverse the array in
    // the range [start, end]
    for (int i = 0; i < mid; i++) {

        // Stores arr[start + i]
        int temp = arr[start + i];

        // Update arr[start + i]
        arr[start + i] = arr[end - i];

        // Update arr[end - i]
        arr[end - i] = temp;
    }
    return;
}

// Utility function to shuffle the given array
// in the of form {a1, b1, a2, b2, ....an, bn}
void shuffleArrayUtil(int arr[], int start, int end)
{
    int i;

    // Stores the length of the array
    int l = end - start + 1;

    // If length of the array is 2
    if (l == 2)
        return;

    // Stores mid of the { start, end }
    int mid = start + l / 2;

    // Divide array into two
    // halves of even length
    if (l % 4) {

        // Update mid
        mid -= 1;
    }

    // Calculate the mid-points of
    // both halves of the array
    int mid1 = start + (mid - start) / 2;
    int mid2 = mid + (end + 1 - mid) / 2;

    // Reverse the subarray made
    // from mid1 to mid2
    reverse(arr, mid1, mid2 - 1);

    // Reverse the subarray made
    // from mid1 to mid
    reverse(arr, mid1, mid - 1);

    // Reverse the subarray made
    // from mid to mid2
    reverse(arr, mid, mid2 - 1);

    // Recursively calls for both
    // the halves of the array
    shuffleArrayUtil(arr, start, mid - 1);
    shuffleArrayUtil(arr, mid, end);
}

// Function to shuffle the given array in
// the form of {a1, b1, a2, b2, ....an, bn}
void shuffleArray(int arr[], int N,
                  int start, int end)
{

    // Function Call
    shuffleArrayUtil(arr, start, end);

    // Print the modified array
    for (int i = 0; i < N; i++)
        printf("%d ", arr[i]);
}

// Driver Code
int main()
{

    // Given array
    int arr[] = { 1, 3, 5, 2, 4, 6 };

    // Size of the array
    int N = sizeof(arr) / sizeof(arr[0]);

    // Shuffles the given array to the
    // required permutation
    shuffleArray(arr, N, 0, N - 1);

    return 0;
}
```

### Java

```java
// Java program for the above approach

class GFG{

// Function to reverse the array from the
// position 'start' to position 'end'
static void reverse(int arr[], int start, int end)
{

    // Stores mid of start and end
    int mid = (end - start + 1) / 2;

    // Traverse the array in
    // the range [start, end]
    for (int i = 0; i < mid; i++)
    {

        // Stores arr[start + i]
        int temp = arr[start + i];

        // Update arr[start + i]
        arr[start + i] = arr[end - i];

        // Update arr[end - i]
        arr[end - i] = temp;
    }
    return;
}

// Utility function to shuffle the given array
// in the of form {a1, b1, a2, b2, ....an, bn}
static void shuffleArrayUtil(int arr[], int start, int end)
{
    int i;

    // Stores the length of the array
    int l = end - start + 1;

    // If length of the array is 2
    if (l == 2)
        return;

    // Stores mid of the { start, end }
    int mid = start + l / 2;

    // Divide array into two
    // halves of even length
    if (l % 4 > 0)
    {

        // Update mid
        mid -= 1;
    }

    // Calculate the mid-points of
    // both halves of the array
    int mid1 = start + (mid - start) / 2;
    int mid2 = mid + (end + 1 - mid) / 2;

    // Reverse the subarray made
    // from mid1 to mid2
    reverse(arr, mid1, mid2 - 1);

    // Reverse the subarray made
    // from mid1 to mid
    reverse(arr, mid1, mid - 1);

    // Reverse the subarray made
    // from mid to mid2
    reverse(arr, mid, mid2 - 1);

    // Recursively calls for both
    // the halves of the array
    shuffleArrayUtil(arr, start, mid - 1);
    shuffleArrayUtil(arr, mid, end);
}

// Function to shuffle the given array in
// the form of {a1, b1, a2, b2, ....an, bn}
static void shuffleArray(int arr[], int N,
                  int start, int end)
{

    // Function Call
    shuffleArrayUtil(arr, start, end);

    // Print the modified array
    for (int i = 0; i < N; i++)
        System.out.printf("%d ", arr[i]);
}

// Driver Code
public static void main(String[] args)
{

    // Given array
    int arr[] = { 1, 3, 5, 2, 4, 6 };

    // Size of the array
    int N = arr.length;

    // Shuffles the given array to the
    // required permutation
    shuffleArray(arr, N, 0, N - 1);

}
}

// This code is contributed by 29AjayKumar
```

## 蟒蛇 3

```python
# Python3 program for the above approach

# Function to reverse the array from the
# position 'start' to position 'end'
def reverse(arr, start, end):

    # Stores mid of start and end
    mid = (end - start + 1) // 2

    # Traverse the array in
    # the range [start, end]
    for i in range(mid):

        # Stores arr[start + i]
        temp = arr[start + i]

        # Update arr[start + i]
        arr[start + i] = arr[end - i]

        # Update arr[end - i]
        arr[end - i] = temp
    return arr

# Utility function to shuffle the given array
# in the of form {a1, b1, a2, b2, ....an, bn}
def shuffleArrayUtil(arr, start, end):
    i = 0

    # Stores the length of the array
    l = end - start + 1

    # If length of the array is 2
    if (l == 2):
        return

    # Stores mid of the { start, end }
    mid = start + l // 2

    # Divide array into two
    # halves of even length
    if (l % 4):

        # Update mid
        mid -= 1

    # Calculate the mid-points of
    # both halves of the array
    mid1 = start + (mid - start) // 2
    mid2 = mid + (end + 1 - mid) // 2

    # Reverse the subarray made
    # from mid1 to mid2
    arr = reverse(arr, mid1, mid2 - 1)

    # Reverse the subarray made
    # from mid1 to mid
    arr = reverse(arr, mid1, mid - 1)

    # Reverse the subarray made
    # from mid to mid2
    arr = reverse(arr, mid, mid2 - 1)

    # Recursively calls for both
    # the halves of the array
    shuffleArrayUtil(arr, start, mid - 1)
    shuffleArrayUtil(arr, mid, end)

# Function to shuffle the given array in
# the form of {a1, b1, a2, b2, ....an, bn}
def shuffleArray(arr, N, start, end):

    # Function Call
    shuffleArrayUtil(arr, start, end)

    # Print the modified array
    for i in arr:
        print(i, end=" ")

# Driver Code
if __name__ == '__main__':

    # Given array
    arr = [1, 3, 5, 2, 4, 6]

    # Size of the array
    N = len(arr)

    # Shuffles the given array to the
    # required permutation
    shuffleArray(arr, N, 0, N - 1)

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;
public class GFG{

// Function to reverse the array from the
// position 'start' to position 'end'
static void reverse(int[] arr, int start, int end)
{

    // Stores mid of start and end
    int mid = (end - start + 1) / 2;

    // Traverse the array in
    // the range [start, end]
    for (int i = 0; i < mid; i++)
    {

        // Stores arr[start + i]
        int temp = arr[start + i];

        // Update arr[start + i]
        arr[start + i] = arr[end - i];

        // Update arr[end - i]
        arr[end - i] = temp;
    }
    return;
}

// Utility function to shuffle the given array
// in the of form {a1, b1, a2, b2, ....an, bn}
static void shuffleArrayUtil(int[] arr, int start, int end)
{

    // Stores the length of the array
    int l = end - start + 1;

    // If length of the array is 2
    if (l == 2)
        return;

    // Stores mid of the { start, end }
    int mid = start + l / 2;

    // Divide array into two
    // halves of even length
    if (l % 4 > 0)
    {

        // Update mid
        mid -= 1;
    }

    // Calculate the mid-points of
    // both halves of the array
    int mid1 = start + (mid - start) / 2;
    int mid2 = mid + (end + 1 - mid) / 2;

    // Reverse the subarray made
    // from mid1 to mid2
    reverse(arr, mid1, mid2 - 1);

    // Reverse the subarray made
    // from mid1 to mid
    reverse(arr, mid1, mid - 1);

    // Reverse the subarray made
    // from mid to mid2
    reverse(arr, mid, mid2 - 1);

    // Recursively calls for both
    // the halves of the array
    shuffleArrayUtil(arr, start, mid - 1);
    shuffleArrayUtil(arr, mid, end);
}

// Function to shuffle the given array in
// the form of {a1, b1, a2, b2, ....an, bn}
static void shuffleArray(int[] arr, int N,
                  int start, int end)
{

    // Function Call
    shuffleArrayUtil(arr, start, end);

    // Print the modified array
    for (int i = 0; i < N; i++)
        Console.Write(arr[i] + " ");
}

// Driver Code
static public void Main ()
{

    // Given array
    int[] arr = { 1, 3, 5, 2, 4, 6 };

    // Size of the array
    int N = arr.Length;

    // Shuffles the given array to the
    // required permutation
    shuffleArray(arr, N, 0, N - 1);

}
}

// This code is contributed by Dharanendra L V
```

## java 描述语言

```javascript
<script>

// Javascript program of the above approach

// Function to reverse the array from the
// position 'start' to position 'end'
function reverse(arr, start, end)
{

    // Stores mid of start and end
    let mid = (end - start + 1) / 2;

    // Traverse the array in
    // the range [start, end]
    for (let i = 0; i < mid; i++)
    {

        // Stores arr[start + i]
        let temp = arr[start + i];

        // Update arr[start + i]
        arr[start + i] = arr[end - i];

        // Update arr[end - i]
        arr[end - i] = temp;
    }
    return;
}

// Utility function to shuffle the given array
// in the of form {a1, b1, a2, b2, ....an, bn}
function shuffleArrayUtil(arr, start, end)
{
    let i;

    // Stores the length of the array
    let l = end - start + 1;

    // If length of the array is 2
    if (l == 2)
        return;

    // Stores mid of the { start, end }
    let mid = start + l / 2;

    // Divide array into two
    // halves of even length
    if (l % 4 > 0)
    {

        // Update mid
        mid -= 1;
    }

    // Calculate the mid-points of
    // both halves of the array
    let mid1 = start + (mid - start) / 2;
    let mid2 = mid + (end + 1 - mid) / 2;

    // Reverse the subarray made
    // from mid1 to mid2
    reverse(arr, mid1, mid2 - 1);

    // Reverse the subarray made
    // from mid1 to mid
    reverse(arr, mid1, mid - 1);

    // Reverse the subarray made
    // from mid to mid2
    reverse(arr, mid, mid2 - 1);

    // Recursively calls for both
    // the halves of the array
    shuffleArrayUtil(arr, start, mid - 1);
    shuffleArrayUtil(arr, mid, end);
}

// Function to shuffle the given array in
// the form of {a1, b1, a2, b2, ....an, bn}
function shuffleArray(arr, N,
                  start, end)
{

    // Function Call
    shuffleArrayUtil(arr, start, end);

    // Print the modified array
    for (let i = 0; i < N; i++)
        document.write(arr[i] + " ");
}

    // Driver Code

    // Given array
    let arr = [ 1, 3, 5, 2, 4, 6 ];

    // Size of the array
    let N = arr.length;

    // Shuffles the given array to the
    // required permutation
    shuffleArray(arr, N, 0, N - 1);

</script>
```

**Output:**

```
1 2 3 4 5 6
```

**时间复杂度:** `O(N * log(N))`
**辅助空间:** `O(1)`