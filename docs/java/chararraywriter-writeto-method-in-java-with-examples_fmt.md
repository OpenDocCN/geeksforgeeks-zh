# Java 中 CharArrayWriter writeTo()方法，带示例

> 原文：[https://www.geeksforgeeks.org/chararraywriter-writeto-method-in-java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-writeto-method-in-java-with-examples/)

Java 中 `CharArrayWriter` 类的 `writeTo(Writer)` 方法用于将 `CharArrayWriter` 的内容写入另一个字符流。

**语法：**

```java
public void writeTo(Writer out)
             throws IOException
```

**参数：** 该方法接受一个参数 `out`，该参数代表作为目标流的输出流。
**返回值：** 此方法不返回值。
**异常：** 如果出现输入输出错误，该方法抛出 `IOException`。

下面的程序说明了 IO 包中 `CharArrayWriter` 类的 `writeTo(Writer)` 方法：

## 示例 1

```java
// Java program to illustrate
// CharArrayWriter writeTo(Writer) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        String str = "GEEKS";

        charArrayWriter.write(str);

        // Create outputStream
        CharArrayWriter out
            = new CharArrayWriter();

        charArrayWriter.writeTo(out);

        // print the outputStream
        System.out.println(
            out.toString());
    }
}
```

**Output：**

```java
GEEKS
```

## 示例 2

```java
// Java program to illustrate
// CharArrayWriter writeTo(Writer) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        charArrayWriter.write("GEEKSFORGEEKS");

        // Create outputStream
        CharArrayWriter out
            = new CharArrayWriter();

        charArrayWriter.writeTo(out);

        // print the outputStream
        System.out.println(
            out.toString());
    }
}
```

**Output：**

```java
GEEKSFORGEEKS
```

**参考文献：**
[https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#writeTo(java.io.Writer)](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#writeTo(java.io.Writer))