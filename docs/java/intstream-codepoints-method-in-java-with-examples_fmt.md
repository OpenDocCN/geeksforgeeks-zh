# Java 中的 IntStream codePoints() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/intstream-codepoints-method-in-java-with-examples/](https://www.geeksforgeeks.org/intstream-codepoints-method-in-java-with-examples/)

`IntStream` 类的 `codePoints()` 方法用于从给定序列中获取代码点值流。它返回作为参数传递的字符的 ASCII 值。

## 语法

```java
public IntStream codePoints()
```

## 返回值

该方法返回输入流代码值。

以下示例说明了 `codePoints()` 方法的使用：

### 例 1

```java
// Java program to demonstrate
// codePoints() method of IntStream class

import java.util.stream.IntStream;

public class GFG {
    public static void main(String args[])
    {

        // String to be converted
        String str = "GeeksForGeeks";

        // Convert the string to code values
        // using codePoints() method
        IntStream stream = str.codePoints();

        System.out.println("ASCII Values are: ");

        // Print the code points
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
ASCII Values are:
```

### 例 2

```java
// Java program to demonstrate
// codePoints() method of IntStream class

import java.util.stream.IntStream;

public class GFG {
    public static void main(String args[])
    {

        // String to be converted
        String str = "A computer science"
                     + " portal for geeks";

        // Convert the string to code values
        // using codePoints() method
        IntStream stream = str.codePoints();

        System.out.println("ASCII Values are: ");

        // Print the code points
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
ASCII Values are:
```