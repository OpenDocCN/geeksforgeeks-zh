# 使用 `getBytes()` 方法将字符串转换为字节数组的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-convert-string-to-byte-array-using-getbytes-method/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-byte-array-using-getbytes-method/)

在 Java 中，字符串是由一个字符数组在内部支持的对象。所以要将一个字符串转换成一个字节数组，我们需要一个 [`getBytes()`](https://www.geeksforgeeks.org/java-lang-string-getbyte-java/) 方法。将字符串转换为字节数组是最简单的方法。该方法使用平台的默认字符集将给定字符串 `t` 转换为字节序列，并返回一个字节数组。它是 `String` 类预定义的函数。但这是一种容易出错的方法，如果平台字符编码与预期编码不匹配，会返回错误的结果。

### 语法

```java
public byte[] getBytes()
```

### 注

*   在此方法中，如果在方法中未指定任何字符编码，则使用平台的默认编码将给定字符串转换为字节数组。
*   字节数组的长度与给定的字符串不同，它取决于字符编码。

## 示例 1

```java
// Java program to illustrate how to
// convert a string to byte array
// Using getBytes()

import java.io.*;

class GFG {

    public static void main(String[] args)
    {

        // Initializing String
        String ss = "Hello GeeksforGeeks";

        // Display the string before conversion
        System.out.println("String: " + ss);

        // Converting string to byte array
        // Using getBytes() method
        byte[] res = ss.getBytes();

        System.out.println("Byte Array:");

        // Display the string after conversion
        for (int i = 0; i < res.length; i++) {
            System.out.print(res[i]);
        }
    }
}
```

### 输出

```java
String: Hello GeeksforGeeks
Byte Array:
```

## 示例 2

```java
// Java program to illustrate how to
// convert a string to byte array
// Using getBytes()

import java.io.*;
import java.util.Arrays;

class GFG {

    public static void main(String[] args)
    {

        // Initializing String
        String ss = "GeeksforGeeks";

        // Display the string before conversion
        System.out.println("String: " + ss);

        // Converting string to byte array
        // Using getBytes() method
        byte[] res = ss.getBytes();

        // Display the string after conversion
        System.out.println("Byte Array:"
                           + Arrays.toString(res));
    }
}
```

### 输出

```java
String: GeeksforGeeks
Byte Array:[71, 101, 101, 107, 115, 102, 111, 114, 71, 101, 101, 107, 115]
```