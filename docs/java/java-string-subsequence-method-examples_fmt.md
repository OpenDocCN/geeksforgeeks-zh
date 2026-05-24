# Java 字符串 `subSequence()` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-string-subsequence-method-examples/](https://www.geeksforgeeks.org/java-string-subsequence-method-examples/)

`java.lang.String.subSequence()` 是 Java 中的一个内置函数，返回一个 `CharSequence`。这个序列的子序列。子序列以指定索引处的字符值开始，以 `(end-1)` 处的字符值结束。返回序列的长度（以字符为单位）是 `(end-start)`，所以如果 `start == end`，则返回一个空序列。

## 语法

```java
public CharSequence subSequence(int start, int end)
```

参数：
- `start` - 这是子序列开始的索引，它是包含性的。
- `end` - 这是子序列结束的索引，它是排除性的。

## 返回

返回范围 `[start, end)` 内的指定子序列。

## 错误和异常

`StringIndexOutOfBoundsException` – 如果 `start` 或 `end` 为负，如果 `end` 大于 `length()`，或者如果 `start` 大于 `end`，它会抛出此错误。

## 程序 1

展示 `java.lang.String.subSequence()` 函数的工作原理。

```java
// Java program to demonstrate working
// of Java.lang.String.subSequence() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        String Str = "Welcome to geeksforgeeks";

        // prints the subsequence from 0-7, exclusive 7th index
        System.out.print("Returns: ");
        System.out.println(Str.subSequence(0, 7));

        System.out.print("Returns: ");
        System.out.println(Str.subSequence(10, 24));
    }
}
```

输出：

```java
Returns: Welcome
Returns:  geeksforgeeks
```

## 程序 2

显示当索引为负时 `java.lang.String.subSequence()` 函数的错误。

```java
// Java program to demonstrate error
// of Java.lang.String.subSequence() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        String Str = "Welcome to geeksforgeeks";

        // throws an error as index is negative
        System.out.print("Returns: ");
        System.out.println(Str.subSequence(-1, 7));
    }
}
```

输出：

```java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: 
String index out of range: -1
    at java.lang.String.substring(String.java:1960)
    at java.lang.String.subSequence(String.java:2003)
    at Gfg.main(File.java:15)
```

## 程序 3

显示当索引超出范围时 `java.lang.String.subSequence()` 函数的错误。

```java
// Java program to demonstrate error
// of Java.lang.String.subSequence() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {

        String Str = "Welcome to geeksforgeeks";

        // throws an error as end is out of range
        System.out.print("Returns: ");
        System.out.println(Str.subSequence(10, 50));
    }
}
```

输出：

```java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: 
String index out of range: 50
    at java.lang.String.substring(String.java:1963)
    at java.lang.String.subSequence(String.java:2003)
    at Gfg.main(File.java:16)
```