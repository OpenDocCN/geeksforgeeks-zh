# 如何用 Java 从 GZIPInputStream 读取数据？

> 原文: [https://www.geeksforgeeks.org/how-to-read-data-from-gzipinputstream-in-java/](https://www.geeksforgeeks.org/how-to-read-data-from-gzipinputstream-in-java/)

Java `GZIPInputStream` 类 (`java.util.zip.GZIPInputStream`) 可用于解压缩使用 GZIP 压缩算法压缩的文件，例如通过 `GZIPOutputStream` 类。

```java
java.lang.Object
    java.io.InputStream
        java.io.FilterInputStream
            java.util.zip.InflaterInputStream
                java.util.zip.GZIPInputStream
```

## 所有实现的接口

`Closeable`, `AutoCloseable`

```java
public class GZIPInputStream
extends InflaterInputStream
```

这个类实现了一个流过滤器，用于读取 GZIP 文件格式的压缩数据。

## 该类的构造函数如下

*   `GZipInputStream(InputStream in)`: 使用默认缓冲区大小创建新的输入流。
*   `GZipInputStream(InputStream in, int size)`: 用指定的缓冲区大小创建新的输入流。

> **注意:** `java.util.zip.GZIPInputStream.read(byte[] buf, int off, int len)` 方法将未压缩的数据读入字节数组。如果 `len` 不为零，该方法将阻塞，直到某些输入可以解压缩；否则，不读取字节，返回 0。

## 本类方法如下

### 方法 1: `close()`

关闭该输入流并释放与该流相关联的任何系统资源。

**返回类型:** `void`

### 方法 2: `read()`

将未压缩的数据读入字节数组。

**参数:**

*   `byte[]`
*   `int off`
*   `int len`

**返回类型:** `int`

### 方法 3: `GZIPInputStream.read(byte[] buf, int off, int len)` 方法

**参数:**

*   `byte[] buf`
*   `int off`
*   `int len`

**语法:**

```java
public int read()
throws IOException
```

**参数**

*   读取数据的缓冲区。
*   目标数组 `b` 中的起始偏移量。
*   读取的最大字节数。

**返回类型:** 实际读取的字节数，如果到达流的末尾，则返回 -1。

**抛出异常:**

*   `NullPointerException` - 如果缓冲区为空。
*   `IndexOutOfBoundsException` 如果 `off` 为负，`len` 为负，或者 `len` 大于 `buf.length - off`。
*   `ZipException` 如果压缩的输入数据损坏。
*   `IOException` - 如果发生了输入/输出错误。

## 示例

### Java 语言

```java
// Java Program to Usage of GZIPInputStream
// via Showcasing Reading Data

// Importing requireeed classes
import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.util.Arrays;
import java.util.zip.DataFormatException;
import java.util.zip.GZIPInputStream;
import java.util.zip.GZIPOutputStream;

// Main class
// GZIPInputStreamDemo
public class GFG {

// Main driver method
    public static void main(String[] args)
        throws DataFormatException, IOException
    {
        // Custom input string
        String message = "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;"
                         + "Welcome to Geeksforgeeks;";

// Print and display the message
        System.out.println("Original Message length : "
                           + message.length());

byte[] input = message.getBytes("UTF-8");

// Compress the bytes
        ByteArrayOutputStream arrayOutputStream
            = new ByteArrayOutputStream();
        GZIPOutputStream outputStream
            = new GZIPOutputStream(arrayOutputStream);
        outputStream.write(input);
        outputStream.close();

// Read and decompress the data
        byte[] readBuffer = new byte[5000];
        ByteArrayInputStream arrayInputStream
            = new ByteArrayInputStream(
                arrayOutputStream.toByteArray());
        GZIPInputStream inputStream
            = new GZIPInputStream(arrayInputStream);
        int read = inputStream.read(readBuffer, 0,
                                    readBuffer.length);
        inputStream.close();
        // Should hold the original (reconstructed) data
        byte[] result = Arrays.copyOf(readBuffer, read);

// Decode the bytes into a String
        message = new String(result, "UTF-8");

System.out.println("UnCompressed Message length : "
                           + message.length());
    }
}
```

**输出**

```java
Original Message length : 250
UnCompressed Message length : 250
```