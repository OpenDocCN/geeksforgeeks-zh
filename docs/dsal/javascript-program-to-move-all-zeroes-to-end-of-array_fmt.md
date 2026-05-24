# 将所有 0 移动到数组末尾的 JavaScript 程序

> 原文：[https://www.geeksforgeeks.org/javascript-program-to-move-all-zeroes-to-end-of-array/](https://www.geeksforgeeks.org/javascript-program-to-move-all-zeroes-to-end-of-array/)

给定一个随机数数组，将给定数组的所有零推到数组的末尾。例如，如果给定的数组是 `{1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0}`，则应该将其更改为 `{1, 9, 8, 4, 2, 7, 6, 0, 0, 0, 0}`。所有其他元素的顺序应该相同。预期时间复杂度为 `O(n)`，额外空间为 `O(1)`。

## 示例

```
Input :  arr[] = {1, 2, 0, 4, 3, 0, 5, 0};
Output : arr[] = {1, 2, 4, 3, 5, 0, 0};

Input : arr[]  = {1, 2, 0, 0, 0, 3, 6};
Output : arr[] = {1, 2, 3, 6, 0, 0, 0};
```

## 算法思路

有很多方法可以解决这个问题。下面是一个简单有趣的方法来解决这个问题。

从左到右遍历给定的数组 `arr`。遍历时，保持数组中非零元素的计数。让计数成为 `count`。对于每个非零元素 `arr[i]`，将该元素置于 `arr[count]` 并递增 `count`。在完成遍历后，所有非零元素已经被转移到前端，`count` 被设置为第一个 0 的索引。现在我们所需要做的就是运行一个循环，使所有元素从 `count` 到数组结束都为零。

## JavaScript 实现

以下是上述方法的实现。

```javascript
// A JavaScript program to move all zeroes at the end of array

// Function which pushes all zeros to end of an array.
function pushZerosToEnd(arr, n)
{
    let count = 0; // Count of non-zero elements

    // Traverse the array. If element encountered is non-
    // zero, then replace the element at index 'count'
    // with this element
    for (let i = 0; i < n; i++)
        if (arr[i] != 0)
            arr[count++] = arr[i]; // here count is
                                // incremented

    // Now all non-zero elements have been shifted to
    // front and 'count' is set as index of first 0.
    // Make all elements 0 from count to end.
    while (count < n)
        arr[count++] = 0;
}

// Driver code
let arr = [1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0, 9];
let n = arr.length;
pushZerosToEnd(arr, n);
document.write("Array after pushing all zeros to end of array :<br>");
for (let i = 0; i < n; i++)
    document.write(arr[i] + " ");

// This code is contributed by Surbhi Tyagi.
```

**输出：**

```
Array after pushing all zeros to end of array :
1 9 8 4 2 7 6 9 0 0 0 0
```

## 复杂度分析

**时间复杂度:** `O(n)`，其中 `n` 为输入数组中的元素个数。
**辅助空间:** `O(1)`

详情请参考[将所有零移到数组末尾](https://www.geeksforgeeks.org/move-zeroes-end-array/)的完整文章！