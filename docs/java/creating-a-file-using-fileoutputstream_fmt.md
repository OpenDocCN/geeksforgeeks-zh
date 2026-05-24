# 使用文件输出流创建文件

> 原文：[https://www.geeksforgeeks.org/creating-a-file-using-fileoutputstream/](https://www.geeksforgeeks.org/creating-a-file-using-fileoutputstream/)

`FileOutputStream` 类属于字节流，以单个字节的形式存储数据。它可以用来创建文本文件。文件表示数据在第二存储介质（如硬盘或光盘）上的存储。文件是否可用或是否可以创建取决于底层平台。尤其是一些平台，一次只允许一个文件输出流（或其他文件写入对象）打开文件进行写入。在这种情况下，如果涉及的文件已经打开，这个类中的构造函数将失败。

`FileOutputStream` 用于写入原始字节流，如图像数据。要编写字符流，请考虑使用文件编写器。

## 重要方法

*   `void close()`: 关闭此 `FileOutputStream` 并释放与此流关联的任何系统资源。
*   `protected void finalize()`: 清理与文件的连接，并确保在没有更多对此流的引用时调用此 `FileOutputStream` 的 `close` 方法。
*   `void write(byte[] b)`: 将指定字节数组中的 `b.length` 个字节写入此 `FileOutputStream`。
*   `void write(byte[] b, int off, int len)`: 将指定字节数组中从偏移量 `off` 开始的 `len` 个字节写入此 `FileOutputStream`。
*   `void write(int b)`: 将指定字节写入此 `FileOutputStream`。

## 按照以下步骤创建一个存储一些字符（或文本）的文本文件

1.  **读取数据：** 首先，应从键盘读取数据。为此，将键盘关联到某个输入流类。使用 `DataInputStream` 类从键盘读取数据的代码如下：

    ```java
    DataInputStream dis = new DataInputStream(System.in);
    ```

    这里 `System.in` 表示与 `DataInputStream` 对象关联的键盘。

2.  **将数据发送到输出流：** 现在，关联一个文件来存储数据。为此，请使用可以向文件发送数据的 `FileOutputStream`。将 `file.txt` 附加到 `FileOutputStream` 可以按如下方式完成：

    ```java
    FileOutputStream fout = new FileOutputStream("file.txt");
    ```

3.  **从 `DataInputStream` 读取数据：** 下一步是从 `DataInputStream` 读取数据并将其写入 `FileOutputStream`。这意味着从 `dis` 对象读取数据并将其写入 `fout` 对象，如下所示：

    ```java
    ch = (char) dis.read();
    fout.write(ch);
    ```

4.  **关闭文件：** 最后，任何文件在执行输入或输出操作后都应关闭，否则数据可能会被破坏。关闭文件是通过关闭相关流来完成的。例如，`fout.close()`：`FileOutputStream` 将被关闭，因此无法再向文件写入数据。

## 执行

如果再次执行程序，`file.txt` 的旧数据将会丢失，任何最近的数据都只存储在文件中。如果我们不想丢失文件的先前数据，而只是将新数据追加到已经存在的数据的末尾，这可以通过在文件名的同时写入 `true` 来实现。

```java
FileOutputStream fout = new FileOutputStream("file.txt", true);
```

## 使用缓冲输出流提高效率

通常，每当我们使用文件输出流将数据写入文件时，如下所示：

```java
fout.write(ch);
```

这里，调用文件输出流将字符写入文件。让我们估算一下从键盘上读取 100 个字符并将它们全部写入一个文件所需的时间。

*   假设使用 `DataInputStream` 从键盘读取数据到内存中，将一个字符读入内存需要 1 秒，然后这个字符由 `FileOutputStream` 写入文件又需要 1 秒。
*   因此，读写一个文件需要 200 秒。这是时间的浪费。另一方面，如果使用缓冲类，它们将提供一个缓冲区，首先将字符填充到缓冲区中，然后这些字符可以立即写入文件。缓冲类应与其他流类结合使用。
*   首先，`DataInputStream` 从键盘读取数据，每个字符花费 1 秒。这个字符被写入缓冲区。因此，将 100 个字符读入缓冲区需要 100 秒的时间。现在，文件输出流将在一个步骤中写入整个缓冲区。因此，读写 100 个字符只需要 101 秒。同样，缓冲流也可以用来提高读取操作的速度。将文件输出流附加到缓冲输出流为：

    ```java
    BufferedOutputStream bout = new BufferedOutputStream(fout, 1024);
    ```

    这里，缓冲区大小声明为 1024 字节。如果未指定缓冲区大小，则使用默认大小 512 字节。

### `BufferedOutputStream` 类的重要方法

*   `void flush()`: 刷新此缓冲输出流。
*   `void write(byte[] b, int off, int len)`: 将指定字节数组中从偏移量 `off` 开始的 `len` 个字节写入此缓冲输出流。
*   `void write(int b)`: 将指定字节写入此缓冲输出流。

## 输出

```java
C:\> javac Create_File.java
C:\> java Create_File
Enter text (@ at the end):
This is a program to create a file
@

C:/> type file.txt
This is a program to create a file
```

## 相关文章

*   [Character Stream vs Byte Stream](https://www.geeksforgeeks.org/character-stream-vs-byte-stream-java/)
*   [File Class in Java](https://www.geeksforgeeks.org/file-class-in-java/)
*   [File Handling in Java using FileWriter and FileReader](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)

本文由 [尼尚·夏尔马](https://www.facebook.com/ChippingEye2766) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。