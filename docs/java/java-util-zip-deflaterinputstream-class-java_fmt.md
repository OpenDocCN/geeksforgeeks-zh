# Java 中的 java.util.zip.DeflaterInputStream 类

> 原文: [https://www.geeksforgeeks.org/java-util-zip-deflaterinputstream-class-java/](https://www.geeksforgeeks.org/java-util-zip-deflaterinputstream-class-java/)

实现一个输入流过滤器，用于以“deflate”压缩格式压缩数据。

## 构造函数和描述

*   `DeflaterInputStream(InputStream in)`: 使用默认的压缩器和缓冲区大小创建一个新的输入流。
*   `DeflaterInputStream(InputStream in, Deflater defl)`: 使用指定的压缩器和默认缓冲区大小创建一个新的输入流。
*   `DeflaterInputStream(InputStream in, Deflater defl, int buflen)`: 使用指定的压缩器和缓冲区大小创建一个新的输入流。

## 方法

*   `int available()`: 到达 EOF 后返回 0，否则始终返回 1。

```java
public int available() throws IOException
```

*   `void close()`: 关闭此输入流及其底层输入流，并丢弃任何未解压的待处理数据。

```java
public void close() throws IOException
```

*   `void mark(int limit)`: 不支持此操作。

```java
public void mark(int limit)
```

*   `boolean markSupported()`: 始终返回 false，因为此输入流不支持 `mark()` 和 `reset()` 方法。

```java
public boolean markSupported()
```

*   `int read()`: 从输入流中读取单个字节的压缩数据。

```java
public int read() throws IOException
```

*   `int read(byte[] b, int off, int len)`: 将压缩数据读入字节数组。

```java
public int read(byte[] b, int off, int len) throws IOException
```

*   `void reset()`: 不支持此操作。

```java
public void reset() throws IOException
```

*   `long skip(long n)`: 跳过并丢弃输入流中的数据。

```java
public long skip(long n) throws IOException
```

## 程序

```java
//Java program to illustrate DeflaterInputStream class
import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.zip.DeflaterInputStream;

class DeflaterInputStreamDemo
{
    public static void main(String[] args) throws IOException
    {
        byte b[] = new byte[10];
        for (byte i = 0; i <10 ; i++)
        {
            b[i] = i;
        }
        ByteArrayInputStream bin = new ByteArrayInputStream(b);
        DeflaterInputStream din = new DeflaterInputStream(bin);

        //illustrating markSupported() method
        System.out.println(din.markSupported());

        //illustrating skip() method
        din.skip(1);

        //illustrating available() method
        System.out.println(din.available());

        //illustrating read(byte[] b,int off,int len)
        byte c[] = new byte[10];
        din.read(c,0,9);
        for (int i = 0; i < 9; i++)
        {
            System.out.print(c[i]);
        }
        while(din.available() == 1)
        {
            //Reads a single byte of compressed data
            System.out.print(din.read());
        }

        System.out.println();
        System.out.println(din.available());

        // illustrating close() method
        din.close();
    }
}
```

## 输出

```java
false

-1009996100981029710199231224400175046-1
```

上述输出代表压缩数据。

**下一篇:** [Java 中的 java.util.zip.DeflaterOutputStream 类](https://www.geeksforgeeks.org/java-util-zip-deflateroutputstream-class-java/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。