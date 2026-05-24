# 使用文件写入器和文件读取器进行 Java 文件处理

> 原文: [https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)

Java `FileWriter` 和 `FileReader` 类用于从文本文件中写入和读取数据（它们是[字符流](https://www.geeksforgeeks.org/character-stream-vs-byte-stream-java/)类）。建议**而不是**使用 `FileInputStream` 和 `FileOutputStream` 类，如果你必须读写任何文本信息，因为这些是字节流类。

## FileWriter

`FileWriter` 对于创建向其中写入字符的文件非常有用。

*   此类继承自 `OutputStreamWriter` 类。
*   这个类的构造函数假设默认字符编码和默认字节缓冲区大小是可以接受的。要自己指定这些值，请在 `FileOutputStream` 上构造一个 `OutputStreamWriter`。
*   `FileWriter` 用于编写字符流。要写入原始字节流，请考虑使用 `FileOutputStream`。
*   如果输出文件还不存在，`FileWriter` 会创建输出文件。

### 构造函数

*   `FileWriter(File file)` – 给定一个 `File` 对象，构造一个 `FileWriter` 对象。
*   `FileWriter(File file, boolean append)` – 给定一个 `File` 对象，构造一个 `FileWriter` 对象。
*   `FileWriter(FileDescriptor FD)` – 构造一个与文件描述符相关联的 `FileWriter` 对象。
*   `FileWriter(String fileName)` – 构造一个给定文件名的 `FileWriter` 对象。
*   `FileWriter(String fileName, boolean append)` – 为给定的文件名构造一个 `FileWriter` 对象，该对象带有一个指示是否追加写入数据的布尔值。

### 方法

*   `public void write(int c) throws IOException` – 写入单个字符。
*   `public void write(char[] cbuf) throws IOException` – 写入字符数组。
*   `public void write(String str) throws IOException` – 写入字符串。
*   `public void write(String str, int off, int len) throws IOException` – 写入字符串的一部分。这里 `off` 是开始写入字符的偏移量，`len` 是要写入的字符数。
*   `public void flush() throws IOException` – 刷新流。
*   `public void close() throws IOException` – 先刷新流，然后关闭编写器。

读和写一个字符一个字符地发生，这增加了输入/输出操作的数量，影响了系统的性能。 `BufferedWriter` 可以和 `FileWriter` 一起使用，提高执行速度。

以下程序描述了如何使用 `FileWriter` 创建文本文件：

```java
// Creating a text File using FileWriter
import java.io.FileWriter;
import java.io.IOException;
class CreateFile
{
    public static void main(String[] args) throws IOException
    {
        // Accept a string 
        String str = "File Handling in Java using "+
                " FileWriter and FileReader";

        // attach a file to FileWriter 
        FileWriter fw=new FileWriter("output.txt");

        // read character wise from string and write 
        // into FileWriter 
        for (int i = 0; i < str.length(); i++)
            fw.write(str.charAt(i));

        System.out.println("Writing successful");
        //close the file 
        fw.close();
    }
}
```

## FileReader

`FileReader` 对于从“文本”文件中读取字符形式的数据非常有用。

*   这个类继承自 `InputStreamReader` 类。
*   这个类的构造函数假定默认的字符编码和默认的字节缓冲区大小是合适的。要自己指定这些值，请在 `FileInputStream` 上构造一个 `InputStreamReader`。
*   `FileReader` 是用来读取字符流的。要读取原始字节流，请考虑使用 `FileInputStream`。

### 构造函数

*   `FileReader(File file)` – 给定要读取的 `File`，创建 `FileReader`。
*   `FileReader(FileDescriptor FD)` – 给定要读取的 `FileDescriptor`，创建一个新的 `FileReader`。
*   `FileReader(String fileName)` – 给定要读取的文件的名称，创建一个新的 `FileReader`。

### 方法

*   `public int read() throws IOException` – 读取单个字符。此方法将一直阻塞，直到某个字符可用、出现输入/输出错误或到达流的末尾。
*   `public int read(char[] cbuff) throws IOException` – 将字符读入数组。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。
*   `public abstract int read(char[] buff, int off, int len) throws IOException` – 将字符读入数组的一部分。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。
    参数:
    `cbuf` – 目标缓冲区
    `off` – 开始存储字符的偏移量
    `len` – 要读取的最大字符数
*   `public void close() throws IOException` – 关闭阅读器。
*   `public long skip(long n) throws IOException` – 跳过字符。此方法将一直阻塞，直到某些字符可用、出现输入/输出错误或到达流的末尾。
    参数:
    `n` – 要跳过的字符数

以下程序描述了如何使用 `FileReader` 读取“文本”文件：

```java
// Reading data from a file using FileReader
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
class ReadFile
{
    public static void main(String[] args) throws IOException
    {
        // variable declaration
        int ch;

        // check if File exists or not
        FileReader fr=null;
        try
        {
            fr = new FileReader("text");
        }
        catch (FileNotFoundException fe)
        {
            System.out.println("File not found");
        }

        // read from FileReader till the end of file
        while ((ch=fr.read())!=-1)
            System.out.print((char)ch);

        // close the file
        fr.close();
    }
}
```

本文由[尼尚夏尔马](https://www.facebook.com/ChippingEye2766)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。