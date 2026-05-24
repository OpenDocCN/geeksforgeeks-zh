# Java 中的 BufferedOutputStream write()方法，示例

> 原文: [https://www.geeksforgeeks.org/bufferedoutputstream-write-method-in-java-with-examples/](https://www.geeksforgeeks.org/bufferedoutputstream-write-method-in-java-with-examples/)

## write(int) 方法

`write(int)` 方法是 `BufferedOutputStream` 类中的方法，用于将指定的字节写入缓冲输出流。这里指定的字节作为整数传递给 `write()` 方法。它用于一次向 `BufferedOutputStream` 写入一个字节。

### 语法

```java
public void write(int b)
            throws IOException
```

### 覆盖

该方法覆盖 `FilterOutputStream` 类的 `write(int)` 方法。

### 参数

该方法接受整数类型的 `b` 作为代表要写入的字节的参数。

### 返回值

此方法不返回值。

### 异常

如果出现输入输出错误，该方法抛出 `IOException`。

下面的程序说明了 `IO` 包中 `BufferedOutputStream` 类的 `write(int)` 方法：

### 程序

```java
// Java program to illustrate
// BufferedOutputStream write(int) method
import java.io.*;
public class GFG {
    public static void main(
        String[] args) throws Exception
    {
        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Convert byteArrayOutputStream to
        // bufferedOutputStream
        BufferedOutputStream buffOutputStr
            = new BufferedOutputStream(
                byteArrayOutStr);

        for (int i = 65; i < 70; i++) {
            // Writes to buffOutputStr
            buffOutputStr.write(i);
        }

        // flush is called
        // to compel bytes to be
        // written out to buffOutputStr
        buffOutputStr.flush();

        for (
            byte by : byteArrayOutStr.toByteArray()) {
            // Converts byte to character
            char ch = (char)by;
            System.out.print(ch);
        }
    }
}
```

### 输出

```java
ABCDE
```

## write(byte[], int, int) 方法

`write(byte[], int, int)` 方法是 `BufferedOutputStream` 类中的方法，用于从指定的字节数组的给定偏移量开始，写入给定长度的字节到缓冲输出流。
基本上，`write()` 方法将给定字节数组中的字节存储到流的缓冲区中，并将缓冲区刷新到主输出流。如果长度等于流的缓冲区大小，则 `write()` 方法刷新缓冲区并将字节直接写入主输出流。

### 语法

```java
public void write(byte[] b,
                  int offset,
                  int length)
            throws IOException
```

### 覆盖

该方法覆盖 `FilterOutputStream` 类中的 `write(byte[], int, int)` 方法。

### 参数

该方法接受三个参数:

*   `b` – 它是字节类型，代表字节数组。
*   `偏移量` – 整数类型，表示字节数组中的起始偏移量。
*   `长度` – 它是整数类型，代表要写入的字节数。

### 返回值

此方法不返回值。

### 异常

如果出现输入输出错误，该方法抛出 `IOException`。

下面的程序说明了 `IO` 包中 `BufferedOutputStream` 类的 `write(byte[], int, int)` 方法：

### 程序

```java
// Java program to illustrate
// BufferedOutputStream write(
// byte[], int, int) method
import java.io.*;
public class GFG {
    public static void main(
        String[] args) throws Exception
    {
        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Convert byteArrayOutputStream to
        // bufferedOutputStream
        BufferedOutputStream buffOutputStr
            = new BufferedOutputStream(
                byteArrayOutStr);

        // Create byte array
        byte b[] = { 71, 69, 69, 75, 83 };

        // Call write(byte[], int, int)
        // method
        // It writes byte array to
        // buffOutputStr
        buffOutputStr.write(b, 0, 5);

        // flush is called
        // to compel bytes to be
        // written out to buffOutputStr
        buffOutputStr.flush();

        for (
            byte by : byteArrayOutStr.toByteArray()) {
            // Converts byte to character
            char ch = (char)by;
            System.out.print(ch);
        }
    }
}
```

### 输出

```java
GEEKS
```

### 参考文献

*   [https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(int))
*   [https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(byte%5B%5D, int, int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(byte%5B%5D, int, int))