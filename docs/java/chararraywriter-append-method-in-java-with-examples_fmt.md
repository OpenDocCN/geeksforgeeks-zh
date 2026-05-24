# Java中CharArrayWriter append()方法示例

> 原文：[https://www.geeksforgeeks.org/chararraywriter-append-method-in-java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-append-method-in-java-with-examples/)

Java中`CharArrayWriter`类的`append()`方法有三种类型：

## 1. append(char)方法

`CharArrayWriter`类的`append(char)`方法用于将指定字符追加到此 writer。此`append()`方法一次追加一个字符到`CharArrayWriter`，并返回此`CharArrayWriter`。

**语法：**

```java
public CharArrayWriter append(char c)
```

**指定者：** 该方法由`Appendable`接口的`append()`方法指定。
**覆盖：** 该方法覆盖`Writer`类的`append()`方法。
**参数：** 该方法接受一个参数`c`，表示要追加的16位字符。
**返回值：** 该方法在追加字符后返回`CharArrayWriter`。
**异常：** 这个方法不抛出任何异常。

下面的程序说明了IO包中`CharArrayWriter`类中的`append(char)`方法：

**程序：**

```java
// Java program to illustrate
// CharArrayWriter append(char) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        // Append the character
        charArrayWriter.append('G');
        charArrayWriter.append('E');
        charArrayWriter.append('E');
        charArrayWriter.append('K');
        charArrayWriter.append('S');

        // print the charArrayWriter
        System.out.println(
            charArrayWriter.toString());
    }
}
```

**输出：**

```java
GEEKS
```