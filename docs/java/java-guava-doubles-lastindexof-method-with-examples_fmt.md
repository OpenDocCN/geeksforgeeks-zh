# 爪哇番石榴 | `Doubles.lastIndexOf()`方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-doubles-lastindexof-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-lastindexof-method-with-examples/)

番石榴库中 `Doubles` 类的 `lastIndexOf()` 方法用于查找双精度数组中给定双精度数值的最后一个索引。要搜索的双精度值和要搜索的双精度数组都作为参数传递给此方法。它返回一个整数值，这是指定双精度值的最后一个索引。如果找不到该值，它将返回 `-1`。

## 语法

```java
public static int lastIndexOf(double[] array,
                              double target)
```

## 参数

该方法接受两个强制参数：

*   `array`：要搜索的双精度数组。
*   `target`：要在双精度数组中通过最后一个索引搜索的双精度值。

## 返回值

该方法返回一个整数值，该整数值是指定双精度值的最后一个索引。如果找不到该值，它将返回 `-1`。

下面的程序说明了这种方法：

### 例 1

```java
// Java code to show implementation of
// Guava's Doubles.lastIndexOf() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a double array
        double[] arr = { 1.2, 2.2, 3.2, 4.2,
                         3.2, 5.6, 3.2, 4.4 };

        double target = 3.2;

        // Using Doubles.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Doubles.lastIndexOf(arr, target);

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

### 输出

```java
Target is present at index 6
```

### 例 2

```java
// Java code to show implementation of
// Guava's Doubles.lastIndexOf() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a double array
        double[] arr = { 1.2, 2.2, 3.2, 4.2,
                         3.2, 5.6, 3.2, 4.4 };

        double target = 10.2;

        // Using Doubles.lastIndexOf() method
        // to get the index of last appearance
        // of a given element in array
        // and return -1 if element is
        // not found in the array
        int index
            = Doubles.lastIndexOf(arr, target);

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

### 输出

```java
Target is not present in the array
```

## 参考

[https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#lastIndexOf(double[], %20double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#lastIndexOf(double[], %20double))