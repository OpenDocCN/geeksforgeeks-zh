# Ints join()函数 | 番石榴 | Java

> 原文: [https://www.geeksforgeeks.org/ints-join-function-guava-java/](https://www.geeksforgeeks.org/ints-join-function-guava-java/)

番石榴的 [`Ints.join()`](https://www.geeksforgeeks.org/ints-class-guava-java/) 返回一个字符串，该字符串包含由分隔符分隔的所提供的 `int` 值。
例如，`join("-", 1, 2, 3)` 返回字符串 `"1-2-3"`。

## 语法

```java
public static String join(String separator, int[] array)
```

## 参数

该方法取以下参数：

*   `separator`: 应该出现在结果字符串中连续值之间的文本（但不在开始或结束处）。
*   `array`: 一组 `int` 值。

## 返回值

该方法返回一个字符串，该字符串包含由 `separator` 分隔的所提供的 `int` 值。

以下示例说明 `Ints.join()` 方法：

## 示例 1

### Java 代码

```java
// Java code to show implementation of
// Guava's Ints.join() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int[] arr = { 2, 4, 6, 8, 10 };

        // Using Ints.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Ints.join(", ", arr));
    }
}
```

### 输出

```java
2, 4, 6, 8, 10
```