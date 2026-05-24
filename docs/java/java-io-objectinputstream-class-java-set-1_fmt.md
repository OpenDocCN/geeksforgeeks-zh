# Java 中的 `Java.io.ObjectInputStream` 类 | 集合 1

> 原文: [https://www.geeksforgeeks.org/java-io-objectinputstream-class-java-set-1/](https://www.geeksforgeeks.org/java-io-objectinputstream-class-java-set-1/)

`ObjectInputStream` 类反序列化之前由 [`ObjectOutputStream`](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/) 编写的原语数据和对象。

*   `ObjectOutputStream` 和 `ObjectInputStream` 都被使用，因为它为对象的图形提供存储。
*   它确保它工作的对象与 JVM 的类相匹配，即 Java 虚拟机。只有那些对象可以从支持`可序列化`或`可外化`输入输出类的流中读取，否则错误。
    `Serializable` 基本上是 JVM(Java 虚拟机)的一种标记，指示它写出流中存在的对象的状态。

## 申报:

```java
public class ObjectInputStream
  extends InputStream
    implements ObjectInput, ObjectStreamConstants
```

## 施工人员:

*   `protected ObjectInputStream()` : 帮助子类不要分配 `ObjectInputStream` 使用的私有数据，如果它们正在重新实现 `ObjectInputStream` 的话。
*   `ObjectInputStream(InputStream source_Input)`: 创建从 `source_Input` 输入流读取数据的 `ObjectInputStream`。

## 方法:

*   `read()`: `Java.io.ObjectInputStream.read()` 读取数据和块的字节，以防没有数据可供读取。
    **语法:**

```java
    public int read()
    Parameters : 
    -----------
    Return : 
    reads byte else, return -1 if end of Stream is detected.
    Exception :
    -> IOException : in case of any IO error occurs.
```

*   `readBoolean()` : `java.io.ObjectInputStream.readBoolean()` reads in a boolean.
    **Syntax :**

```java
    public int readBoolean()
    Parameters : 
    -----------
    Return : 
    reads in a boolean.
    Exception :
    -> IOException : in case of any IO error occurs.
    -> EOFException : if end of the stream is reached.
```

```java
    // Java program explaining the working of read(), readBoolean() method

import java.io.*;

public class NewClass
    {
        public static void main(String[] args) throws IOException
        {
            // create a new file with an ObjectOutputStream and ObjectInputStream
            FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");

ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);
            ObjectInputStream Geek_inStream = 
                            new ObjectInputStream(new FileInputStream("GEEKS.txt"));

// Methods covered in later
            geek_outStream.writeBoolean(true);
            geek_outStream.writeUTF("Geeks For Geeks");
            geek_outStream.flush();

// Use of readBoolean() 
            System.out.println("USe of readBoolean() : " + Geek_inStream.readBoolean());

System.out.print("Use of read() method in Java : ");

// Use of read() method : reading the content of file
            for (int i = 0; i < Geek_inStream.available();)
            {
                System.out.print((char) Geek_inStream.read());
            }

}
    }
```

**输出:**

```java
    USe of readBoolean() : true
    Use of read() method in Java : Geeks For Geeks
```

*   `read(byte[] buffer, int offset, int maxlen)` : `java.io.ObjectInputStream.read(byte[] buffer, int offset, int maxlen)` reads part of data from the `buffer` starting from offset position upto maxlen position of the buffer.
    **Syntax :**

```java
    public int read(byte[] buffer, int offset, int maxlen)
    Parameters : 
    buffer : buffer to be read
    offset : starting position of the buffer
    maxlen : max. no. of bytes to be read
    Return : 
    reads 'maxlen' bytes of data else, return -1 if end of Stream is detected.
    Exception :
    -> IOException : in case of any IO error occurs.
```

```java
    // Java program explaining the working of
    // read(byte[] buffer, int offset, int maxlen)

import java.io.*;

public class NewClass
    {
        public static void main(String[] args) throws IOException
        {
            // create a new file with an ObjectOutputStream and ObjectInputStream
            FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");

ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

// create an ObjectInputStream for the file we created before
            ObjectInputStream Geek_inStream
                = new ObjectInputStream(new FileInputStream("GEEKS.txt"));
```

# Java ObjectInputStream 方法详解

## 代码示例

```java
geek_outStream.writeUTF("GeeksForGeeks");
geek_outStream.flush();

byte[] buffer = new byte[25];

// Use of read(byte[] buffer, int offset, int maxlen)
Geek_inStream.read(buffer, 2, 20);

System.out.print("Use of read(buffer, offset, maxlen) : ");
for (int i = 0; i < 19; i++)
{
    System.out.print((char)buffer[i]);
}
}
}
```

**输出:**

```java
GeeksForGeeks
```

## readByte()

`java.io.ObjectInputStream.readByte()` 读取 8 位字节。

**语法:**

```java
public byte readByte()
Parameters:
-----------
Return:
reads 8-bit byte.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readChar()

`java.io.ObjectInputStream.readChar()` 读取 16 位字符。

**语法:**

```java
public int read()
Parameters:
-----------
Return:
reads 16-bit of char.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readDouble()

`java.io.ObjectInputStream.readDouble()` 读取 64 位 double。

**语法:**

```java
public double readDouble()
Parameters:
Return:
reads 64 bit double.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readFloat()

`java.io.ObjectInputStream.readFloat()` 读取 32 位浮点。

**语法:**

```java
public float readFloat()
Parameters:
-----------
Return:
reads a 32 bit float.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readInt()

`java.io.ObjectInputStream.readInt()` 读取 32 位 Int。

**语法:**

```java
public int readInt()
Parameters:
-----------
Return:
reads a 32 bit int.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readLong()

`java.io.ObjectInputStream.readLong()` 读取 64 位 long。

**语法:**

```java
public long readLong()
Parameters:
-----------
Return:
reads a 64 bit long.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## 综合示例

```java
// Java program explaining the working of
// readChar(), writeByte(), writeDouble(),
// writeFloat(), writeInt(), writeLong()

import java.io.*;

public class NewClass
{
    public static void main(String[] args) throws IOException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        // create an ObjectInputStream for the file we created before
        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeChar('G');
        geek_outStream.writeByte('G');
        geek_outStream.writeDouble(00436754746);
        geek_outStream.writeFloat(2.12345f);
        geek_outStream.writeInt(3576);
        geek_outStream.writeLong(368723776);

        geek_outStream.flush();

        // Use of readChar()
        System.out.println("Use of readChar() : " + Geek_inStream.readChar());

        // Use of readByte() :
        System.out.println("Use of readByte() : " + Geek_inStream.readByte());

        // Use of readDouble() :
        System.out.println("Use of readDouble() : " + Geek_inStream.readDouble());

        // Use of readFloat() :
        System.out.println("Use of readFloat() : " + Geek_inStream.readFloat());

        // Use of readInt() :
        System.out.println("Use of readInt() : " + Geek_inStream.readInt());

        // Use of readLong() :
        System.out.println("Use of readLong() : " + Geek_inStream.readLong());
    }
}
```

**输出:**

```java
Use of readChar() : G
Use of readByte() : 71
Use of readDouble() : 7.5225574E7
Use of readFloat() : 2.12345
Use of readInt() : 3576
Use of readLong() : 368723776
```

## readUnsignedByte()

`java.io.ObjectInputStream.readUnsignedByte()` 读取无符号的 8 位字节。

**语法:**

```java
public int readUnsignedByte()
Parameters:
-----------
Return:
reads an unsigned 8 bit byte.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## readUnsignedShort()

`java.io.ObjectInputStream.readUnsignedShort()` 读取无符号的 16 位 short。

**语法:**

```java
public int readUnsignedShort()
Parameters:
-----------
Return:
reads an unsigned 16 bit short.
Exception:
-> `IOException`: in case of any IO error occurs.
-> `EOFException`: if end of the stream is reached.
```

## 无符号读取示例

```java
// Java program explaining the working of
// readUnsignedByte() and readUnsignedShort()

import java.io.*;

public class NewClass
{
    public static void main(String[] args) throws IOException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        // create an ObjectInputStream for the file we created before
        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeByte(111);
        geek_outStream.writeShort(121212);

        geek_outStream.flush();

        // Use of readUnsignedByte()
        System.out.println("readUnsignedByte() : "
                        + Geek_inStream.readUnsignedByte());

        // Use of readUnsignedShort() :
        System.out.println("readUnsignedShort() : "
                        + Geek_inStream.readUnsignedShort());
    }
}
```

**输出:**

```java
readUnsignedByte() : 111
readUnsignedShort() : 55676
```

## readUTF()

`java.io.ObjectInputStream.readUTF()` 以修改后的 UTF-8（Unicode 转换格式）格式读取字符串。UTF-8 表示它使用 8 位块来表示一个字符。

**语法:**

```java
public String readUTF()
Parameters:
public final Object readObject()
Return:
reads String in modified UTF-8 (Unicode Transformation Format) format
Exception:
-> `IOException`: in case of any IO error occurs.
```

## readUTF 示例

```java
// Java program explaining the working of readUTF()

import java.io.*;

public class NewClass
{
    public static void main(String[] args) throws IOException, ClassNotFoundException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeUTF("gEEKSArehERE");
        geek_outStream.flush();

        // Use of readUTF() method
        System.out.println("Use of readUTF() : " + Geek_inStream.readUTF());
    }
}
```

**输出:**

```java
Use of readUTF() : gEEKSArehERE
```

## skipBytes()

`java.io.ObjectInputStream.skipBytes(int maxlen)` 在读取时跳过“maxlen”字节数。

**语法:**

```java
public int skipBytes(int maxlen)
Parameters:
maxlen: max. no. of bytes to be skipped
Return:
no. of bytes to be skipped
Exception:
-> `IOException`: in case of any IO error occurs.
```

## skipBytes 示例

```java
// Java program explaining the working of skipBytes()

import java.io.*;
```

# Java ObjectInputStream 方法详解

## skipBytes() 方法

```java
public class NewClass
{
    public static void main(String[] args) throws IOException, ClassNotFoundException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeUTF("gEEKSArehERE");
        geek_outStream.flush();

        // Use of skipBytes() :
        Geek_inStream.skipBytes(7);

        for (int i = 2; i < Geek_inStream.available(); i++)
        {
            System.out.print((char) Geek_inStream.readByte());
        }
    }
}
```

**输出:**

```java
Are
```

## readFully() 方法

### readFully(byte[] destination)

**`java.io.ObjectInputStream.readFully(byte[] destination)`** 从源读取所有字节到目标数组。

**语法:**

```java
public void readFully(byte[] destination)
```

**参数:**
- `destination` : 数据要读入的缓冲区

**返回值:**
- 无返回值 (`void`)

**异常:**
- `IOException` : 发生任何IO错误时抛出。
- `EOFException` : 如果到达流末尾。

**示例代码:**

```java
// Java program explaining the working of readFully()

import java.io.*;

public class NewClass
{
    public static void main(String[] args) throws IOException, ClassNotFoundException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeUTF("gEEKSArehERE");
        geek_outStream.flush();

        byte[] destination = new byte[14];

        // Use of readFully()
        Geek_inStream.readFully(destination);

        String str = new String(destination);
        System.out.println("Use of readFully(destination, offset, maxlen) : "+str);
    }
}
```

**输出:**

```java
Use of readFully(destination, offset, maxlen) : gEEKSArehERE
```

### readFully(byte[] destination, int offset, int maxlen)

**`java.io.ObjectInputStream.readFully(byte[] destination, int offset, int maxlen)`** 从源读取一些字节（从 `offset` 到 `maxlen` 位置）到目标数组。

**语法:**

```java
public void readFully(byte[] destination, int offset, int maxlen)
```

**参数:**
- `destination` : 数据要读入的缓冲区
- `offset` : 缓冲区的起始位置
- `maxlen` : 要读取的最大字节数

**返回值:**
- 无返回值 (`void`)

**异常:**
- `IOException` : 发生任何IO错误时抛出。
- `EOFException` : 如果到达流末尾。

**示例代码:**

```java
// Java program explaining the working of
// readFully(byte[] destination, int offset, int maxlen)

import java.io.*;

public class NewClass
{
    public static void main(String[] args) throws IOException, ClassNotFoundException
    {
        // create a new file with an ObjectOutputStream and ObjectInputStream
        FileOutputStream geek_out = new FileOutputStream("GEEKS.txt");
        ObjectOutputStream geek_outStream = new ObjectOutputStream(geek_out);

        ObjectInputStream Geek_inStream
                    = new ObjectInputStream(new FileInputStream("GEEKS.txt"));

        geek_outStream.writeUTF("gEEKSArehERE");
        geek_outStream.flush();

        byte[] destination = new byte[14];

        // Use of readFully(byte[] destination, int offset, int maxlen)
        Geek_inStream.readFully(destination, 3, 7);

        String str = new String(destination);
        System.out.println("Use of readFully(destination, offset, maxlen) : "+ str);
    }
}
```

**输出:**

```java
Use of readFully(destination, offset, maxlen) : geeks
```

---

本文由 **莫希特·古普塔供稿🙂** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。