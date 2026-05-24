# 如何在 Java 中将字符串转换为 Int？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-a-string-to-an-int-in-java/](https://www.geeksforgeeks.org/how-to-convert-a-string-to-an-int-in-java/)

给定包含数字作为字符的字符串，任务是在 Java 中将这个给定的字符串转换成整数。

## 示例

```java
Input: str = "1234"
Output: 1234

Input: str = "213s"
Output: 0
Since the String contains other than digits,
hence the integer value will be 0
```

## 方法 1：使用 `Integer.parseInt()` 方法

这是将 `String` 转换为整数最简单的方法。此函数将字符串参数解析为有符号的十进制整数。

### 语法

```java
public static int parseInt(String s)
            throws NumberFormatException
```

下面是上述方法的实现：

```java
// Java program to convert String to int
// using Integer.parseInt() method

import java.io.*;

class GFG {

    // Function to convert String to integer
    public static int convert(String str)
    {
        int val = 0;
        System.out.println("String = " + str);

        // Convert the String
        try {
            val = Integer.parseInt(str);
        }
        catch (NumberFormatException e) {

            // This is thrown when the String
            // contains characters other than digits
            System.out.println("Invalid String");
        }
        return val;
    }

    // Driver code
    public static void main(String[] args)
    {

        String str = "1234";
        int val = convert(str);
        System.out.println("Integer value = " + val);
        System.out.println();

        str = "123s";
        val = convert(str);
        System.out.println("Integer value = " + val);
    }
}
```

### 输出

```java
String = 1234
Integer value = 1234

String = 123s
Invalid String
Integer value = 0
```

## 方法 2：使用 Guava 库的 `Ints::tryParse` 方法

另一种将 `String` 转换为整数的方法是使用 Guava 库的 `Ints::tryParse` 方法。它与 `Integer.parseInt()` 方法类似，但此方法更简洁、更强大。

### 语法

```java
public static Integer tryParse(String s)
```

下面是上述方法的实现：

```java
// Java program to convert String to int
// using Ints::tryParse method

import java.io.*;
import java.util.*;
import com.google.common.primitives.Ints;

class GFG {

    // Function to convert String to integer
    public static int convert(String str)
    {
        int val = 0;
        System.out.println("String = " + str);

        // Convert the String
        val = Optional.ofNullable(str)
                  .map(Ints::tryParse)
                  .orElse(0);

        return val;
    }

    // Driver code
    public static void main(String[] args)
    {

        String str = "1234";
        int val = convert(str);
        System.out.println("Integer value = " + val);
        System.out.println();

        str = "123s";
        val = convert(str);
        System.out.println("Integer value = " + val);
    }
}
```

### 输出

```java
String = 1234
Integer value = 1234

String = 123s
Integer value = 0
```