# Java 中的 Java.io.LineNumberReader 类

> 原文: [https://www.geeksforgeeks.org/java-io-linenumberreader-class-java/](https://www.geeksforgeeks.org/java-io-linenumberreader-class-java/)

跟踪行号的缓冲字符输入流。这个类定义了 `setLineNumber(int)` 和 `getLineNumber()` 方法，分别用于设置和获取当前行号。

*   默认情况下，行号从 0 开始。读取数据时，行号在每个行终止符处递增，也可以通过调用 `setLineNumber(int)` 来更改。
*   但请注意，`setLineNumber(int)` 并不会实际改变流中的当前位置；它只改变 `getLineNumber()` 将返回的值。
*   行被认为是由换行符 (`'\n'`)、回车符 (`'\r'`) 或回车符后紧跟换行符中的任意一个结束的。

## 构造函数

*   `LineNumberReader(Reader in)`: 使用默认的输入缓冲区大小创建一个新的 `LineNumberReader`。
*   `LineNumberReader(Reader in, int sz)`: 创建一个新的 `LineNumberReader`，将字符读入给定大小的缓冲区。

## 方法

*   `getLineNumber()`: 获取当前行号。

```java
Syntax: public int getLineNumber()
Returns: The current line number
```

*   `mark(int readAheadLimit)`: 标记流中的当前位置。后续对 `reset()` 的调用将尝试将流重新定位到此点，并相应地重置行号。

```java
Syntax: public void mark(int readAheadLimit) throws IOException
Parameters:
    readAheadLimit - Limit on the number of characters that may be read while still preserving the mark. After reading this many characters, attempting to reset the stream may fail.
Throws:
    IOException
```

*   `read()`: 读取单个字符。行终止符被压缩成单个换行符 (`'\n'`)。每当读取行终止符时，当前行号递增。

```java
Syntax: public int read() throws IOException
Returns:
    The character read, or -1 if the end of the stream has been reached
Throws:
    IOException
```

*   `read(char[] cbuf, int off, int len)`: 将字符读入数组的一部分。每当读取行终止符时，当前行号递增。

```java
Syntax: public int read(char[] cbuf, int off, int len) throws IOException
Parameters:
    cbuf - Destination buffer
    off - Offset at which to start storing characters
    len - Maximum number of characters to read
Returns:
    The number of bytes read, or -1 if the end of the stream has already been reached
Throws:
    IOException
```

*   `readLine()`: 读取一行文本。每当读取行终止符时，当前行号递增。

```java
Syntax: public String readLine() throws IOException
Returns: A String containing the contents of the line, not including any line termination characters, or null if the end of the stream has been reached
Throws:
    IOException
```

*   `reset()`: 将流重置到最近的标记处。

```java
Syntax: public void reset() throws IOException
Throws:
    IOException
```

*   `setLineNumber(int lineNumber)`: 设置当前行号。

```java
Syntax: public void setLineNumber(int lineNumber)
Parameters:
    lineNumber - An int specifying the line number
```

*   `skip(long n)`: 跳过字符。

```java
Syntax: public long skip(long n) throws IOException
Parameters:
    n - The number of characters to skip
Returns:
    The number of characters actually skipped
Throws:
    IOException
    IllegalArgumentException
```

## 程序

```java
//Java program demonstrating LineNumberReader methods
import java.io.FileReader;
import java.io.IOException;
import java.io.LineNumberReader;
class LineNumberReaderDemo
{
    public static void main(String[] args) throws IOException 
    {
        FileReader fr = new FileReader("file.txt");
        LineNumberReader lnr = new LineNumberReader(fr);
        char c[] = new char[20];

        //illustrating setLineNumber()
        lnr.setLineNumber(0);

        //illustrating getLineNumber()
        System.out.println(lnr.getLineNumber());

        //illustrating markSupported() method
        if(lnr.markSupported())
        {
            System.out.println("mark() method is supported");
            //illustrating mark method
            lnr.mark(100);
        }

        /*File Contents
        * This is first line
        this is second line
        This is third line
        */

        //skipping 19 characters
        lnr.skip(19);

        //illustrating ready() method
        if(lnr.ready())
        {
            //illustrating readLine() method
            System.out.println(lnr.readLine());

            //illustrating read(char c[],int off,int len)
            lnr.read(c);
            for (int i = 0; i <20 ; i++)
            {
                System.out.print(c[i]);
            }

            //illustrating reset() method
            lnr.reset();

            for (int i = 0; i <18 ; i++)
            {
                //illustrating read() method
                System.out.print((char)lnr.read());
            }
            int ch;

            //illustrating read() method
            System.out.println(lnr.readLine());
            while((ch = lnr.read())!=-1)
                System.out.print((char)ch);
        }

        //close the stream
        lnr.close();
    }
}
```

## 输出

```
mark() method is supported
this is second line
This is third line
This is first line
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。