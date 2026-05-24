# 压缩和解压缩 Java 中的文件

> 原文：[https://www.geeksforgeeks.org/compressing-and-decompressing-files-in-java/](https://www.geeksforgeeks.org/compressing-and-decompressing-files-in-java/)

Java 中提供了 `DeflaterOutputStream` 和 `InflaterOutputStream` 类来压缩和解压缩文件内容。这些类提供了可用于压缩文件内容的有用方法。

## 使用 `DeflaterOutputStream` 压缩文件

这个类实现了一个输出流过滤器，用于以“deflate”压缩格式压缩数据。它还被用作其他类型的压缩过滤器的基础，例如 `GZIPOutputStream`。

### 重要方法

*   `void close()`：将剩余的压缩数据写入输出流，并关闭底层流。
*   `protected void deflate()`：将下一个压缩数据块写入输出流。
*   `void finish()`：完成向输出流写入压缩数据，而不关闭底层流。
*   `void flush()`：刷新压缩的输出流。
*   `void write(byte[] b, int off, int len)`：将字节数组写入压缩输出流，其中 `off` 是数据的起始偏移量，`len` 是字节总数。
*   `void write(int b)`：向压缩的输出流写入一个字节。

### 压缩文件的步骤（文件 1）

*   获取一个输入文件 `File1`，将其赋值给 `FileInputStream` 用于读取数据。
*   获取输出文件 `File2` 并将其赋值给 `FileOutputStream`。这将有助于将数据写入 `File2`。
*   将 `FileOutputStream` 赋值给 `DeflaterOutputStream` 以压缩数据。
*   现在，从 `FileInputStream` 读取数据并将其写入 `DeflaterOutputStream`。它将压缩数据并发送到 `FileOutputStream`，然后 `FileOutputStream` 会将压缩后的数据存储在输出文件中。

```java
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.Deflater;
import java.util.zip.DeflaterOutputStream;

class zip
{
    public static void main(String[] args) throws IOException {
        //Assign the original file : file to
        //FileInputStream for reading data
        FileInputStream fis=new FileInputStream("file1");

        //Assign compressed file:file2 to FileOutputStream
        FileOutputStream fos=new FileOutputStream("file2");

        //Assign FileOutputStream to DeflaterOutputStream
        DeflaterOutputStream dos=new DeflaterOutputStream(fos);

        //read data from FileInputStream and write it into DeflaterOutputStream
        int data;
        while ((data=fis.read())!=-1)
        {
            dos.write(data);
        }

        //close the file
        fis.close();
        dos.close();
    }
}
```

## 使用 `InflaterInputStream` 解压缩文件

这个类实现了一个流过滤器，用于以“deflate”压缩格式解压缩数据。它还被用作其他解压缩过滤器的基础，如 `GZIPInputStream`。

### 重要方法

*   `int available()`：到达 EOF 后返回 0，否则始终返回 1。
*   `void close()`：关闭输入流并释放与该流关联的任何系统资源。
*   `protected void fill()`：用更多用于解压缩的数据填充输入缓冲区。
*   `void mark(int readlimit)`：在输入流中的当前位置做标记。
*   `boolean markSupported()`：测试输入流是否支持 `mark` 和 `reset` 方法。
*   `int read()`：读取一个字节的解压缩数据。
*   `int read(byte[] b, int off, int len)`：将解压缩的数据读入字节数组，其中 `off` 是数据的初始偏移量，`len` 是字节总数。
*   `void reset()`：将此流重新定位到上次调用 `mark` 方法时的位置。

### 解压文件的步骤

*   名为 `File2` 的文件现在包含压缩数据，我们需要从这个文件中获取原始的解压缩数据。
*   将压缩文件 `File2` 赋值给 `FileInputStream`。这有助于从 `File2` 读取数据。
*   将输出文件 `File3` 赋值给 `FileOutputStream`。这将有助于将未压缩的数据写入 `File3`。
*   现在，从 `InflaterInputStream` 读取未压缩的数据并将其写入 `FileOutputStream`。这将把未压缩的数据写入 `File3`。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.InflaterInputStream;

//Uncompressing a file using an InflaterInputStream
class unzip
{
    public static void main(String[] args) throws IOException {
        //assign Input File : file2 to FileInputStream for reading data
        FileInputStream fis=new FileInputStream("file2");

        //assign output file: file3 to FileOutputStream for reading the data
        FileOutputStream fos=new FileOutputStream("file3");

        //assign inflaterInputStream to FileInputStream for uncompressing the data
        InflaterInputStream iis=new InflaterInputStream(fis);

        //read data from inflaterInputStream and write it into FileOutputStream
        int data;
        while((data=iis.read())!=-1)
        {
            fos.write(data);
        }

        //close the files
        fos.close();
        iis.close();
    }
}
```

本文由 [尼尚夏尔马](https://www.facebook.com/ChippingEye2766) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。