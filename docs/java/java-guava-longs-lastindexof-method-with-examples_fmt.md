# Guava Longs.lastIndexOf() 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-longs-lastindexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-lastindexof-method-with-examples/)

Guava 库中 `Longs` 类的 `lastIndexOf()` 方法用于查找长数组中给定长值的最后一个索引。要搜索的长值和要搜索的长数组都作为参数传递给此方法。它返回一个整数值，这是指定长值的最后一个索引。如果找不到该值，它将返回 `-1`。

## 语法

```java
public static int lastIndexOf(long[] array,
                              long target)
```

## 参数

该方法接受两个强制参数：

*   `array`：要搜索的长值数组。
*   `target`：要在长数组中搜索其最后一个索引的长值。

## 返回值

该方法返回一个整数值，该整数值是指定长值的最后一个索引。如果找不到该值，它将返回 `-1`。

下面的程序说明了这种方法：

### 示例 1

```java
// Java code to show implementation of
// Guava's Longs.lastIndexOf() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 1, 2, 3, 4, 3, 5, 3, 4 };

        long target = 3;

        // Using Longs.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Longs.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

**输出：**

```java
Target is present at index 6
```

### 示例 2

```java
// Java code to show implementation of
// Guava's Longs.lastIndexOf() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a long array
        long[] arr = { 3, 5, 7, 11, 13 };

        long target = 17;

        // Using Longs.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Longs.lastIndexOf(arr, target);

        if (index != -1) {
            System.out.println("Target is present"
                               + " at index "
                               + index);
        }
        else {
            System.out.println("Target is not present"
                               + " in the array");
        }
    }
}
```

**输出：**

```java
Target is not present in the array
```

## 参考

[https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#lastIndexOf-long:A-long-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#lastIndexOf-long:A-long-)