# Java 中输入流和输出流的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-inputstream-and-outputstream-in-java/](https://www.geeksforgeeks.org/difference-between-inputstream-and-outputstream-in-java/)

一个**流**可以定义为数据的序列或者连续的数据流。流是处理输入/输出的一种清晰的方式。流有两种类型，如下所示:

![Stream in Java](img/438df84d61e82ea43980892a59222917.png)

在上图中，我们的输入流和输出流将驻留在字节流中。所以让我们讨论字节流。

## 字节流

字节流提供了一种处理字节输入和输出的便捷方式。字节流被进一步划分为不同的类，但是最上层的类描述如下:

![ByteStream in Java](img/e122e760389cb3da57f46310005ff67a.png)

### InputStream

`InputStream` 是描述流输入的字节流的抽象类，用于读取，可以是文件、图像、音频、视频、网页等。没关系。因此，`InputStream` 一次从一个源项目中读取数据。

![Input Stream in Java](img/25a88ba3d0ed3ee2322727409d5f114d.png)

### OutputStream

`OutputStream` 是描述流输出的字节流的抽象类，用于将数据写入文件、图像、音频等。因此，输出流一次向目标写入一个数据。

![OutputStream in Java](img/74b397a64b7bcf132a65816bbf1cc1e5.png)

## 输入流和输出流的区别

<figure class="table">

| **InputStream** | **OutputStream** |
| --- | --- |
| 1. 这是一个描述流输入的抽象类。 | 1. 这是一个描述流输出的抽象类。 |
| 2. 输入流一次从源中读取一次数据。 | 2. 输出流一次将数据写入目标。 |
| 3. 输入流由执行以下操作方法组成:<br>    * 从输入流中读取下一个字节的数据，并在文件末尾返回-1: `public abstract int read() throws IOException`<br>    * 关闭当前输入流: `public int available() throws IOException`<br>    * 返回可从当前输入流中读取的字节数的估计值: `public void close() throws IOException` | 3. 输出流由执行以下操作的方法组成:<br>    * 向当前输出流写入一个字节: `public void write(int) throws IOException`<br>    * 将字节数组写入当前输出流: `public void write(byte[]) throws IOException`<br>    * 刷新当前输出流: `public void flush() throws IOException`<br>    * 关闭当前输出流: `public void close() throws IOException` |
| 4. 输入流的类型有:<br>    * `FileInputStream`<br>    * `ByteArrayInputStream`<br>    * `FilterInputStream`<br>    * `ObjectInputStream`<br>    在这些类型中，最重要和最常用的类型是 `FileInputStream`。 | 4. 输出流的类型有:<br>    * `FileOutputStream`<br>    * `ByteArrayOutputStream`<br>    * `FilterOutputStream`<br>    * `ObjectOutputStream`<br>    在这些类型中，最重要和最常用的类型是 `FileOutputStream`。 |

</figure>

## 输入流的程序

在本程序中，文件 `gfg.txt` 由“GEEKSFORGEKS”组成。

**注意:** 如果文件保存在保存 Java 程序的相同位置，那么按照下面的程序操作。如果文件保存在某个特定的位置，那么写下细节。

```java
FileInputStream fileIn=new FileInputStream("C:\\gfg.txt"); 
```

```java
// Imported to use methods
import java.io.FileInputStream;

// Main Class
public class InputStreamExample {
    public static void main(String args[])
    {
        // Reading from Source file
        try {
            FileInputStream fileIn
                = new FileInputStream("gfg.txt");
            int i = 0;
            while ((i = fileIn.read()) != -1) {
                System.out.print((char)i);
            }
            fileIn.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
GEEKSFORGEEKS 
```

## 输出流程序

这里 `gfg.txt` 文件为空，保存在保存 Java 程序的相同位置。这个程序在空文件中写入 GeeksforGeeks，如果在文件中成功写入文本，将显示消息“文件成功更新”。

```java
// Imported to use inbuilt methods
import java.io.FileOutputStream;

// Main class
public class OutputStreamExample {
    public static void main(String args[])
    {
        // Writing in file gfg.txt
        try {
            FileOutputStream fileOut
                = new FileOutputStream("gfg.txt");
            String s = "GeeksforGeeks";

            // converting string into byte array
            byte b[] = s.getBytes();
            fileOut.write(b);
            fileOut.close();
            System.out.println(
                "file is successfully updated!!");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
file is successfully updated!!
```

当我们再次使用第一个程序读取文件时，输出如下所示:

```
GeeksforGeeks
```