# Ints.contains() 函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/ints-contains-function-guava-java/](https://www.geeksforgeeks.org/ints-contains-function-guava-java/)

Guava 的 [`Ints.contains()`](https://www.geeksforgeeks.org/ints-class-guava-java/) 函数，如果目标值作为元素出现在数组中的任何位置，则返回 `true`。

**语法：**
```java
public static boolean contains(int[] array, int target)
```

**参数：** 该方法接受以下参数：
*   `array`：`int` 值的数组，可能为空。
*   `target`：一个原始 `int` 值。

**返回值：** 这个方法返回一个布尔值。如果存在索引 `i` 使得 `array[i] == target`，则返回 `true`。

**示例 1：**

## Java 实现

```java
// Java code to show implementation of
// Guava's Ints.contains() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an Integer array
        int[] arr = { 5, 4, 3, 2, 1 };

        int target = 3;

        // Using Ints.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Ints.contains(arr, target))
            System.out.println("Target is present"
                               + " in the array");
        else
            System.out.println("Target is not present"
                               + " in the array");
    }
}
```

**输出：**
```java
Target is present in the array
```