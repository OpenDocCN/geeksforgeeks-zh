# Java 中的 Java.io.DataInputStream 类|集合 2

> 原文:[https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-2/](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-2/)

[Java 中的 Java.io.DataInputStream 类|集合 1](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-1/)

## 更多方法

*   `byte readByte()`: 读取并返回一个输入字节。

```java
public final byte readByte() throws IOException
```
返回值：此输入流的下一个字节，作为一个有符号的8位字节。
抛出异常：
`EOFException`
`IOException`

*   `float readFloat()`: 读取四个输入字节并返回一个浮点值。

```java
public final float readFloat() throws IOException
```
返回值：此输入流的接下来四个字节，解释为一个`float`。
抛出异常：`EOFException`
`IOException`

*   `void readFully(byte[] b)`: 从输入流中读取一些字节，并将它们存储到缓冲区数组`b`中。

```java
public final void readFully(byte[] b) throws IOException
```
参数：`b` - 读取数据的缓冲区。
抛出异常：`EOFException`
`IOException`

*   `void readFully(byte[] b, int off, int len)`: 从输入流中读取`len`个字节。

```java
public final void readFully(byte[] b,
                 int off,
                 int len) throws IOException
```
参数：`b` - 读取数据的缓冲区。
`off` - 数据的起始偏移量。
`len` - 要读取的字节数。
抛出异常：`EOFException`
`IOException`

*   `String readLine()`: 从输入流中读取下一行文本。

```java
public final String readLine() throws IOException
```
返回值：此输入流的下一行文本。
抛出异常：`IOException`
*已弃用 此方法不能正确地将字节转换为字符。*

*   `long readLong()`: 读取8个输入字节并返回一个`long`值。

```java
public final long readLong() throws IOException
```
返回值：此输入流的接下来八个字节，解释为一个`long`。
抛出异常：
`EOFException`
`IOException`

*   `short readShort()`: 读取两个输入字节并返回一个`short`值。

```java
public final short readShort() throws IOException
```
返回值：此输入流的接下来两个字节，解释为一个有符号的16位数字。
抛出异常：
`EOFException`
`IOException`

*   `String readUTF()`: 读取以修改后的UTF-8格式编码的字符串。

```java
public final String readUTF() throws IOException
```
返回值：一个Unicode字符串。
抛出异常：`EOFException`
`IOException`
`UTFDataFormatException`

*   `int skipBytes(int n)`: 尝试跳过输入流中的`n`个字节数据并丢弃跳过的字节。

```java
public final int skipBytes(int n) throws IOException
```
参数：`n` - 要跳过的字节数。
返回值：实际跳过的字节数。
抛出异常：
`IOException`

## 节目 2

```java
//Java program to demonstrate DataInputStream
// This program uses try-with-resources. It requires JDK 7 or later.
import java.io.*;
import java.lang.reflect.Array;
import java.util.Arrays;

class DataInputStreamDemo
{
    public static void main(String args[]) throws IOException
    {
        //writing the data.
        try ( DataOutputStream dout =
                    new DataOutputStream(new FileOutputStream("file.dat")) )
        {
            dout.writeBytes("1");
            dout.writeFloat(4.4545f);
            dout.writeUTF("geeksforgeeks");
            dout.writeChars("GeeksforGeeks\n");
            dout.writeBytes("ABCDEFG");
        }
        catch(FileNotFoundException ex)
        {
            System.out.println("Cannot Open the Output File");
            return;
        }

        // reading the data back.
        try ( DataInputStream din =
                    new DataInputStream(new FileInputStream("file.dat")) )
        {
            //illustrating readByte() method
            byte t=din.readByte();

            //illustrating readFloat() method
            float u=din.readFloat();

            //illustrating readUTF() method
            String temp=din.readUTF();

            //illustrating readLine() method
            String temp1=din.readLine();

            System.out.println("Values: " + t +" "+" "+u+" "+temp+" "+temp1 );

            //illustrating skipBytes() method
            //skipping "AB"
            din.skipBytes(2);

            //illustrating readFully() method
            byte[] b=new byte[4];
            din.readFully(b,0,4);
            System.out.println(Arrays.toString(b));
        }
        catch(FileNotFoundException e)
        {
            System.out.println("Cannot Open the Input File");
            return;
        }
    }
}
```

## 输出

```java
Values: 49  4.4545 geeksforgeeks  GeeksforGeeks 
[67, 68, 69, 70]
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。