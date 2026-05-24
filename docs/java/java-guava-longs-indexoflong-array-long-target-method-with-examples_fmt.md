# Java 番石榴 | `Longs.indexOf(long[] array, long[] target)` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-longs-indexoflong-array-long-target-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-indexoflong-array-long-target-method-with-examples/)

`Longs.indexOf(long[] array, long[] target)` 方法是 Guava 的 [`Longs`](https://www.geeksforgeeks.org/longs-class-guava-java/) 类接受两个参数 `array` 和 `target`。如果目标存在于数组中，该方法返回其第一次出现的开始位置。如果数组中不存在目标，则该方法返回 `-1`。

## 语法

```java
public static int indexOf(long[] array, long[] target)
```

## 参数

该方法接受两个参数：

*   `array`：是检查目标数组索引的整数数组。
*   `target`：作为指定数组的子序列进行搜索的数组。

## 返回值

该方法返回如下整数值：

*   如果数组中存在目标数组，则返回目标首次出现的起始位置。
*   否则，如果数组中没有目标，则返回 `-1`。

## 异常

该方法不抛出任何异常。

下面的例子说明了上述方法的实现：

## 例 1

```java
// Java code to show implementation of
// Guava's Longs.indexOf(long[] array,
// long[] target) method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an long array
        long[] arr = { 1, 2, 3, 4, 3, 5 };

        long[] target = { 3, 4, 3 };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Longs.indexOf(long[] array, long[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Longs.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present "
                               + "in the array");
        }
    }
}
```

输出：

```java
Array: [1, 2, 3, 4, 3, 5]
Target Array: [3, 4, 3]
Target is present at index 2
```

## 例 2

```java
// Java code to show implementation of
// Guava's Longs.indexOf(long[] array,
// long[] target) method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an long array
        long[] arr = { 3, 5, 7, 11, 13 };

        long[] target = { 23, 37 };

        System.out.println("Array: "
                           + Arrays.toString(arr));

        System.out.println("Target Array: "
                           + Arrays.toString(target));

        // Using Longs.indexOf(long[] array, long[] target)
        // method to get the start position of the first
        // occurrence of the specified target within array,
        // or -1 if there is no such occurrence.
        int index = Longs.indexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

输出：

```java
Array: [3, 5, 7, 11, 13]
Target Array: [23, 37]
Target is not present in the array
```

参考：[https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#indexOf-long:A-long:A-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#indexOf-long:A-long:A-)