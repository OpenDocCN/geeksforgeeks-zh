# Java 中的 `FileInputStream` 类

> 原文: [https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)

[`FileInputStream`](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/) 类对于以字节序列的形式从文件中读取数据非常有用。`FileInputStream` 用于读取原始字节流，如图像数据。要读取字符流，请考虑使用 `FileReader`。

## `FileInputStream` 类的构造函数

1.  `FileInputStream(File file)`: 创建从指定 `File` 对象读取的输入文件流。
2.  `FileInputStream(FileDescriptor fdobj)`: 创建从指定文件描述符读取的输入文件流。
3.  `FileInputStream(String name)`: 创建输入文件流，以从具有指定名称的文件中读取。

## `FileInputStream` 类的方法

| 方法 | 执行的操作 |
| --- | --- |
| `available()` | 返回从此输入流中可以读取（或跳过）的剩余字节数的估计值。 |
| `close()` | 关闭此文件输入流并释放与该流关联的任何系统资源。 |
| `finalize()` | 确保在没有更多引用时调用此文件输入流的 `close` 方法。 |
| `getChannel()` | 返回与此文件输入流关联的唯一 `FileChannel` 对象。 |
| `getFD()` | 返回一个 `FileDescriptor` 对象，该对象表示与此 `FileInputStream` 正在使用的文件系统中的实际文件的连接。 |
| `read()` | 从此输入流中读取一个字节的数据。 |
| `read(byte[] b)` | 从此输入流中读取最多 `b.length` 字节的数据到一个字节数组中。 |
| `read(byte[] b, int off, int len)` | 从此输入流中读取最多 `len` 字节的数据到字节数组中。 |
| `skip(long n)` | 跳过输入流中的 `n` 字节数据。 |

现在，当我们使用这些方法时，我们通常会按照以下步骤使用 `FileInputStream` 从文件中读取数据，这是文件输入类的最终目标。

**步骤 1:** 将文件附加到 `FileInputStream`，因为这将使我们能够从文件中读取数据，如下所示:

```java
FileInputStream fileInputStream = new FileInputStream("file.txt");
```

**步骤 2:** 现在为了从文件中读取数据，我们应该从 `FileInputStream` 中读取数据，如下所示:

```java
ch = fileInputStream.read();
```

**步骤 3-A:** 当没有更多数据可供进一步读取时，`read()` 方法返回 -1；

**步骤 3-B:** 那么我们应该将监视器附加到输出流上。为了显示数据，我们可以使用 `System.out.print`。

```java
System.out.print(ch);
```

## 实现

*原始文件内容:*

```java
This is my first line
This is my second line
```

## 示例

```java
// Java Program to Demonstrate FileInputStream Class

// Importing I/O classes
import java.io.*;

// Main class
// ReadFile
class GFG {

    // Main driver method
    public static void main(String args[])
        throws IOException
    {
        // Attaching the file to FileInputStream
        FileInputStream fin
            = new FileInputStream("file1.txt");

        // Illustrating getChannel() method
        System.out.println(fin.getChannel());

        // Illustrating getFD() method
        System.out.println(fin.getFD());

        // Illustrating available method
        System.out.println("Number of remaining bytes:"
                           + fin.available());

        // Illustrating skip() method
        fin.skip(4);

        // Display message for better readability
        System.out.println("FileContents :");

        // Reading characters from FileInputStream
        // and write them
        int ch;

        // Holds true till there is data inside file
        while ((ch = fin.read()) != -1)
            System.out.print((char)ch);

        // Close the file connections
        // using close() method
        fin.close();
    }
}
```

## 输出

```java
sun.nio.ch.FileChannelImpl@1540e19d
java.io.FileDescriptor@677327b6
Number of remaining bytes:45
FileContents :
 is my first line
This is my second line
```

`BufferedInputStream` 可用于从文件中一次读取充满数据的缓冲区。这提高了执行速度。

本文由 [**尼尚·夏尔马**](https://www.facebook.com/ChippingEye2766?ref=bookmarks) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。