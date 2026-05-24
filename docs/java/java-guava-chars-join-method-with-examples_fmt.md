# Java 番石榴 | `Chars.join()` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-chars-join-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-join-method-with-examples/)

番石榴库中 `Chars` 类的 `join()` 方法用于组合或连接所有由**分隔符**分隔的给定 `char` 值。这些字符值被作为参数传递给这个方法。此方法还将分隔符作为参数。此方法返回一个字符串，该字符串是对指定字符值进行联接操作的结果。

> **例如：** `join("-", 1L, 2L, 3L)` 返回字符串 `"1-2-3"`。

## 语法

> `public static String join(String separator, char... array)`

## 参数

该方法接受两个强制参数：

*   **分隔符：** 出现在连接的字符值之间的字符。
*   **数组：** 是要连接的字符值的数组。

## 返回值

这个方法返回一个包含所有给定字符值的字符串，由 `分隔符` 分隔。

下面的程序说明了这种方法的使用：

### 例 1

```java
// Java code to show implementation of
// Guava's Chars.join() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a char array
        char[] arr = { 'a', 'b', 'c', 'd', 'e' };

        // Using Chars.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Chars.join("#", arr));
    }
}
```

**Output:**

```java
a#b#c#d#e
```

### 例 2

```java
// Java code to show implementation of
// Guava's Chars.join() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a char array
        char[] arr = { 'G', 'E', 'E', 'K', 'S' };

        // Using Chars.join() method to get a
        // string containing the elements of array
        // separated by a separator
        System.out.println(Chars.join("*", arr));
    }
}
```

**Output:**

```java
G*E*E*K*S
```

## 参考

[https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#join(java.lang.String, %20char...)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#join(java.lang.String, %20char...))