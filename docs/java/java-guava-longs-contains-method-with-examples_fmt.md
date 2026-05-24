# Java 番石榴 `Longs.contains()` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-longs-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-contains-method-with-examples/)

番石榴的 [`Longs`](https://www.geeksforgeeks.org/longs-class-guava-java/) 类的 `contains()` 方法用于检查数组中是否存在某个值，即目标值。该目标值和数组被作为该方法的参数。此方法返回一个布尔值，该值表示目标值是否存在于数组中。

**语法：**

```java
public static boolean contains(long[] array, 
                               long target)
```

**参数：** 该方法接受两个参数：

*   `array`：是要搜索目标值的 long 类型数组。
*   `target`：是要检查其是否存在的 long 类型值。

**返回值：** 该方法返回 `true` 如果对于某个 `i`，`i`<sup>th</sup> 索引处存在的值等于目标值，否则返回 `false`。

**异常：** 该方法不抛出任何异常。

**例 1：**

```java
// Java code to show implementation of
// Guava's Longs.contains() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 5L, 4L, 3L, 2L, 1L };

        long target = 3L;

        // Using Longs.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Longs.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not "
                               + "present in the array");
    }
}
```

**输出：**

```java
Target is present in the array
```

**例 2：**

```java
// Java code to show implementation of
// Guava's Longs.contains() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 2L, 4L, 6L, 8L, 10L };

        long target = 7L;

        // Using Longs.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Longs.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not "
                               + "present in the array");
    }
}
```

**输出：**

```java
Target is not present in the array
```

**参考：** [https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#contains-long:A-long-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#contains-long:A-long-)