# Java IO 文件阅读器类

> 原文：[https://www.geeksforgeeks.org/java-io-filereader-class/](https://www.geeksforgeeks.org/java-io-filereader-class/)

`FileReader`是`java.io`包中的一个类，可以用来从文件中读取字符流。此类使用指定的字符集或平台的默认字符集来解码字节到字符。

**字符集：** 字符集类用于定义产生编码器和解码器的方法，以及恢复与字符集结合的几个名称的方法。

**默认字符集：** 默认字符集是在隐式计算机启动期间定义的，它取决于底层操作系统的区域设置和字符集。

下图显示了文件阅读器类的层次流。

![](img/80bb72caf1ae5283f6e704e82a11bde4.png)

**文件阅读器类的分层流程**

## 构造器

`FileReader`的构造函数如下表所示。

| 构造器 | 描述 |
| --- | --- |
| `FileReader(File file)` | 使用给定的`File`对象创建一个新的`FileReader`（使用默认字符集）。 |
| `FileReader(FileDescriptor fd)` | 使用给定的`FileDescriptor`创建一个新的`FileReader`。 |
| `FileReader(String fileName)` | 使用给定的文件名创建一个新的`FileReader`（使用默认字符集）。 |
| `FileReader(String fileName, Charset charset)` | 使用给定的文件名创建一个新的`FileReader`（使用指定的`Charset`）。 |

## 方法

`FileReader`的主要方法如下表所示。

*   `read()`: 读取并返回单个字符，如果已到达流的末尾，则返回`-1`。
*   `read(char[] charBuffer, int offset, int length)`: 读取字符流，并将它们存储在给定的字符缓冲区`charBuffer`中。`offset`是开始存储的位置，`length`是要读取的字符总数。如果已到达流的末尾，它会返回已读取的字符数或`-1`。
*   `ready()`: 告知流是否准备好被读取。如果一个流的输入缓冲区非空，那么这个流就是就绪的。
*   `getEncoding()`: 返回流正在使用的字符编码的名称。
*   `close()`: 关闭流并释放与之关联的系统资源。

## Java 代码示例

```java
// Java program to show the usage of
// IO FileReader Class
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            FileReader fileReader
                = new FileReader("gfg.txt");

            System.out.println("Reading char by char : \n");
            int i;
            while ((i = fileReader.read()) != -1) {
                System.out.print((char)i);
            }

            System.out.println("Reading using array : \n");
            char[] charArray = new char[10];
            fileReader.read(charArray);
            System.out.print(charArray);

            fileReader.close();
            System.out.println("FileReader closed!");
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
Reading char by char :
GeeksForGeeks
Reading using array :
GeeksForGeeks
FileReader closed!
```