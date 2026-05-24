# 用 Java 编写 `CharArrayWriter()` 方法，示例

> 原文：[https://www.geeksforgeeks.org/chararraywriter-write-method-in-java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-write-method-in-java-with-examples/)

## Java 中 `CharArrayWriter` 类的 `write()` 方法有三种类型

### 1. `write(int)` 方法

`CharArrayWriter` 类的 `write(int)` 方法用于以整数的形式向写入器写入一个字符。此 `write()` 方法一次向 `CharArrayWriter` 写入一个字符。

**语法：**

```java
public void write(int c)
```

**覆盖：** 该方法覆盖 `Writer` 类的 `write()` 方法。
**参数：** 该方法接受一个参数 `c`，代表要写入的整数。
**返回值：** 此方法不返回值。
**异常：** 此方法不抛出任何异常。

下面的程序说明了 IO 包中 `CharArrayWriter` 类的 `write(int)` 方法：

**程序：**

```java
// Java program to illustrate
// CharArrayWriter write(int) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        // Write the character
        charArrayWriter.write(71);
        charArrayWriter.write(69);
        charArrayWriter.write(69);
        charArrayWriter.write(75);
        charArrayWriter.write(83);

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