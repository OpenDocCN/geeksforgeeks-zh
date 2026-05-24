# 打印数组中最小元素的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-print-the-smallest-element-in-an-array/](https://www.geeksforgeeks.org/java-program-to-print-the-smallest-element-in-an-array/)

`Java` 提供了一个数据结构，数组，存储了相同类型的数据集合。它是相同类型元素的固定大小的顺序集合。

**例：**

```java
arr1[] = {2 , -1 , 9 , 10}
output : -1

arr2[] = {0, -10, -13, 5}
output : -13
```

**我们需要在这个程序中找到并打印一个数组的最小值元素。**

1.  通过维护一个 `min element` 并在遍历整个数组时更新它，如果我们遇到一个小于 `min` 的数。
2.  通过对数组进行排序，并打印排序后数组的第 0 个索引元素。

## 方法 1：维护一个最小元素

维护一个 `min element`，如果我们遇到一个小于最小的数，在遍历整个数组时更新它。

```java
// Java program to print the smallest element of the array

public class FindSmallestElementInArray {
    public static void main(String[] args)
    {
        // Either we can initialize array elements or can
        // get input from user. Always it is best to get
        // input from user and form the array
        int[] initializedArray
            = new int[] { 25, 110, 74, 75, 5 };

        System.out.println("Given array ");

        for (int i = 0; i < initializedArray.length; i++) {
            System.out.println(initializedArray[i]);
        }

        // Initialize minValue with first element of array.
        int minValue = initializedArray[0];

        // Loop through the array
        for (int i = 0; i < initializedArray.length; i++) {
            // Compare elements of array with minValue and
            // if condition true, make minValue to that
            // element
            if (initializedArray[i] < minValue)
                minValue = initializedArray[i];
        }

        System.out.println(
            "Smallest element present in given array: "
            + minValue);
    }
}
```

**输出**

```java
Given array

Smallest element present in given array: 5
```

*   **时间复杂度：** `O(n)`
*   **空间复杂度：** `O(1)`

## 方法 2：对数组进行排序

通过对数组进行排序，并在排序后打印数组的第 0 个索引元素。

```java
// Java program to print the smallest element of the array

import java.util.*;

public class FindSmallestElementInArray {
    public static void main(String[] args)
    {
        // we can initialize array elements
        int[] initializedArray = new int[] { 25, 110, 74, 75, 5 };

        System.out.println("Given array ");
        for (int i = 0; i < initializedArray.length; i++) {
            System.out.println(initializedArray[i]);
        }

        // sort the array
        Arrays.sort(initializedArray);

        int minValue = initializedArray[0];

        System.out.println(
            "Smallest element present in given array: "
            + minValue);
    }
}
```

**输出**

```java
Given array

Smallest element present in given array: 5
```

*   **时间复杂度：** `O(NlogN)` 因为排序花费的时间是 `nlogn`，数组中有 `n` 个元素。
*   **空间复杂度：** `O(1)`