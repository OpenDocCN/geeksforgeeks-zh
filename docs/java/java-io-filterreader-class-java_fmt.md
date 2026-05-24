# Java 中的 Java.io.FilterReader 类

> 原文: [https://www.geeksforgeeks.org/java-io-filterreader-class-java/](https://www.geeksforgeeks.org/java-io-filterreader-class-java/)

用于读取过滤字符流的抽象类。抽象类 `FilterReader` 本身提供默认方法，将所有请求传递给包含的流。`FilterReader` 的子类应该覆盖这些方法中的一些，并且还可以提供额外的方法和字段。

## 构造方法

*   **`protected FilterReader(Reader in)`**：创建新的 `FilterReader`。

## 方法

*   **`void close()`**：关闭流并释放与其相关联的任何系统资源。一旦流被关闭，进一步的 `read()`、`ready()`、`mark()`、`reset()` 或 `skip()` 调用将引发 `IOException`。关闭以前关闭的流没有效果。

    ```java
    public void close() throws IOException
    ```
    抛出:
    `IOException`

*   **`void mark(int readAheadLimit)`**：标记流中的当前位置。

    ```java
    public void mark(int readAheadLimit) throws IOException
    ```
    参数:
    `readAheadLimit` - 在仍然保留标记的情况下可以读取的字符数限制。读取这么多字符后，尝试重置流可能会失败。
    抛出:
    `IOException`

*   **`boolean markSupported()`**：告知此流是否支持 `mark()` 操作。

    ```java
    public boolean markSupported()
    ```
    返回:
    当且仅当此流支持标记操作时返回 `true`。

*   **`int read()`**：读取单个字符。

    ```java
    public int read() throws IOException
    ```
    返回: 读取的字符，作为范围在 0 到 65535 (0x00-0xffff) 之间的整数，如果已到达流的末尾则返回 -1。
    抛出:
    `IOException`

*   **`int read(char[] cbuf, int off, int len)`**：将字符读入数组的一部分。

    ```java
    public int read(char[] cbuf, int off, int len) throws IOException
    ```
    参数:
    `cbuf` - 目标缓冲区
    `off` - 开始存储字符的偏移量
    `len` - 要读取的最大字符数
    返回:
    读取的字符数，如果已到达流的末尾则返回 -1。
    抛出: `IOException`

*   **`boolean ready()`**：告知该流是否准备好被读取。

    ```java
    public boolean ready() throws IOException
    ```
    返回:
    如果保证下一个 `read()` 不会因输入而阻塞，则返回 `true`，否则返回 `false`。注意，返回 `false` 并不保证下一个读取会阻塞。
    抛出: `IOException`

*   **`void reset()`**：重置流。

    ```java
    public void reset() throws IOException
    ```
    抛出:
    `IOException`

*   **`long skip(long n)`**：跳过字符。

    ```java
    public long skip(long n) throws IOException
    ```
    参数:
    `n` - 要跳过的字符数
    返回:
    实际跳过的字符数
    抛出:
    `IOException`

## 程序示例

```java
//Java program illustrating FilterReader class methods

import java.io.*;
class FilterReaderdemo
{
    public static void main(String[] args) throws IOException
    {
        Reader r = new StringReader("GeeksforGeeks");
        FilterReader fr = new FilterReader(r) 
        {
        };
        char ch[] = new char[8];

        //illustrating markSupported()
        if(fr.markSupported())
        {
            //illustrating mark() method
            System.out.println("mark method is supported");
            fr.mark(100);
        }

        //illustrating skip() method
        fr.skip(5);

        //illustrating ready()
        if(fr.ready())
        {
            //illustrating read(char[] cbuff,int off,int len)
            fr.read(ch);
            for (int i = 0; i < 8; i++) 
            {
                System.out.print(ch[i]);
            }

            //illustrating reset()
            fr.reset();
            for (int i = 0; i <5 ; i++)
            {
                //illustrating read()
                System.out.print((char)fr.read());
            }
        }

        //closing the stream
        fr.close();
    }
}
```

## 输出

```java
mark method is supported
forGeeksGeeks
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。