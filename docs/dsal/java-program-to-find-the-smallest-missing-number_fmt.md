# Java 程序查找最小缺失数

> 原文：`https://www.geeksforgeeks.org/java-program-to-find-the-smallest-missing-number/`

给定一个由 `n` 个不同整数组成的排序的数组，其中每个整数都在 `0` 到 `m-1` 和 `m > n` 的范围内。找出数组中缺少的最小数字。

## 例子

```
Input: {0, 1, 2, 6, 9}, n = 5, m = 10 
Output: 3

Input: {4, 5, 10, 11}, n = 4, m = 12 
Output: 0

Input: {0, 1, 2, 3}, n = 4, m = 5 
Output: 4

Input: {0, 1, 2, 3, 4, 5, 6, 7, 10}, n = 9, m = 11 
Output: 8
```

感谢拉维钱德拉提出以下两种方法。

## 方法 1（使用二分搜索法）

为 `i = 0` 至 `m-1`，在数组中做二分搜索法查找 `i`。如果数组中没有 `i`，则返回 `i`。
时间复杂度：`O(m log n)`

## 方法 2（线性搜索）

如果 `arr[0]` 不是 `0`，返回 `0`。否则，从索引 `0` 开始遍历输入数组，对于每对元素 `a[i]` 和 `a[i+1]`，找出它们之间的区别。如果差值大于 `1`，则 `a[i]+1` 是缺失的数字。
时间复杂度：`O(n)`

## 方法三（使用改良二分搜索法）

感谢亚辛和杰姆提出这个方法。
在标准二分搜索法过程中，将待搜索元素与中间元素进行比较，根据比较结果，我们决定是搜索结束，还是前往左半部分或右半部分。
在该方法中，我们修改了标准二分搜索法算法，将中间元素与其索引进行比较，并在此基础上进行决策。

*   如果第一个元素与其索引不同，则返回第一个索引。
*   否则得到中间指数，比如说中间。
    *   如果 `arr[mid]` 大于 `mid`，则所需元素位于左半部分。
    *   否则所需元素位于右半部分。

### Java 实现

```
class SmallestMissing 
{
    int findFirstMissing(int array[], int start, int end) 
    {
        if (start > end)
            return end + 1;

        if (start != array[start])
            return start;

        int mid = (start + end) / 2;

        // Left half has all elements from 0 to mid
        if (array[mid] == mid)
            return findFirstMissing(array, mid+1, end);

        return findFirstMissing(array, start, mid);
    }

    // Driver program to test the above function
    public static void main(String[] args) 
    {
        SmallestMissing small = new SmallestMissing();
        int arr[] = {0, 1, 2, 3, 4, 5, 6, 7, 10};
        int n = arr.length;
        System.out.println("First Missing element is : "
                + small.findFirstMissing(arr, 0, n - 1));
    }
}
```

### 输出

```
Smallest missing element is 8
```

**注意：** 如果数组中有重复的元素，这个方法不起作用。
**时间复杂度：** `O(Logn)`

## 另一种方法

思路是用递归二分搜索法找到最小的缺失数。下面是借助步骤的图示：

*   如果数组的第一个元素不是 `0`，那么最小的缺失数就是 `0`。
*   如果数组的最后一个元素是 `N-1`，那么最小的缺失数就是 `N`。
*   否则，从第一个和最后一个索引中找到中间元素，并检查中间元素是否等于所需元素。即 `first + mid_index`。
    *   如果中间元素是所需的元素，则最小的缺失元素位于中间的右侧搜索空间中。
    *   否则，最小的缺失数在中间的左边搜索空间。

下面是上述方法的实现：

### Java 实现

```
// Java Program for above approach
import java.io.*;

class GFG 
{
    // Program to find Smallest 
    // Missing in Sorted Array
    int findSmallestMissinginSortedArray(
                            int[] arr) 
    { 
        // Check if 0 is missing 
        // in the array
        if(arr[0] != 0)
            return 0;

        // Check is all numbers 0 to n - 1 
        // are present in array
        if(arr[arr.length-1] == arr.length - 1)
            return arr.length;

        int first = arr[0];

        return findFirstMissing(arr,0,
                        arr.length-1,first);
    }

    // Program to find missing element 
    int findFirstMissing(int[] arr , int start , 
                            int end, int first) 
    {
        if (start < end) 
        {
            int mid = (start+end)/2;

            /** Index matches with value 
            at that index, means missing
            element cannot be upto that point */
            if (arr[mid] != mid+first)
                return findFirstMissing(arr, start, 
                                        mid , first);
            else
                return findFirstMissing(arr, mid+1, 
                                        end , first);
        }
        return start+first;
    }

    // Driver program to test the above function
    public static void main(String[] args) 
    {
        GFG small = new GFG();
        int arr[] = {0, 1, 2, 3, 4, 5, 7};
        int n = arr.length;

        // Function Call
        System.out.println("First Missing element is : "
            + small.findSmallestMissinginSortedArray(arr));
    }
}
```

### 输出

```
First Missing element is : 6
```

**时间复杂度：** `O(Logn)`

详情请参考寻找最小缺失数整篇文章！