# 二进制插入排序的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-for-binary-insertion-sort/](https://www.geeksforgeeks.org/java-program-for-binary-insertion-sort/)

我们可以使用二分搜索法减少[正常插入排序](https://www.geeksforgeeks.org/insertion-sort/)中的比较次数。二进制插入排序使用二分搜索法在每次迭代中查找插入所选项目的正确位置。
在正常插入中，排序在最坏的情况下需要 `O(i)`（第一次迭代）。我们可以通过使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)将其减少到 `O(logi)`。

## Java 实现

```java
// Java Program implementing
// binary insertion sort

import java.util.Arrays;
class GFG
{
    public static void main(String[] args)
    {
        final int[] arr = {37, 23, 0, 17, 12, 72, 31,
                             46, 100, 88, 54 };

        new GFG().sort(arr);

        for(int i=0; i<arr.length; i++)
            System.out.print(arr[i]+" ");
    }

    public void sort(int array[])
    {
        for (int i = 1; i < array.length; i++)
        {
            int x = array[i];

            // Find location to insert using binary search
            int j = Math.abs(Arrays.binarySearch(array, 0, i, x) + 1);

            //Shifting array to one location right
            System.arraycopy(array, j, array, j+1, i-j);

            //Placing element at its correct location
            array[j] = x;
        }
    }
}

// Code contributed by Mohit Gupta_OMG
```

更多详情请参考[二进制插入排序](https://www.geeksforgeeks.org/binary-insertion-sort/)整篇文章！