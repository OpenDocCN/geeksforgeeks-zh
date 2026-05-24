# Java.io.RandomAccessFile 类方法集合 1

> 原文：[https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-1/](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-1/)

**`Java.io.RandomAccessFile`** 类提供了一种使用读写操作随机访问文件的方法。它像存储在文件中的字节数组一样工作。

## 声明

```java
public class RandomAccessFile
   extends Object
      implements DataOutput, DataInput, Closeable
```

## 随机访问文件类的方法

### 1. `read()`
**`Java.io.RandomAccessFile.read()`** 从文件中读取字节数据。该字节作为 0-255 范围内的整数返回。

```java
Syntax :
public int read()
Parameters : 
--------
Return  :
reads byte of data from file, -1 if end of file is reached.
```

### 2. `read(byte[] b)`
**`Java.io.RandomAccessFile.read(byte[] b)`** 从缓冲区读取 `b.length` 以内的字节。

```java
Syntax :
public int read(byte[] b)
Parameters : 
b : buffer to be read
Return  :
byte of data from file upto b.length, -1 if end of file is reached.
```

### 3. `read(byte[] b, int offset, int len)`
**`Java.io.RandomAccessFile.read(byte[] b, int offset, int len)`** 从缓冲区读取从 `offset` 位置初始化到 `b.length` 的字节。

```java
Syntax :
public int read(byte[] b, int offset, int len)
Parameters : 
b : buffer to read
offset : starting position to read
len : max no of bytes to read
Return  :
reads bytes initialising from offset position upto b.length from the buffer.
```

### 4. `readBoolean()`
**`Java.io.RandomAccessFile.readBoolean()`** 从文件中读取一个布尔值。

```java
Syntax :
public final boolean readBoolean()
Parameters : 
------
Return  :
boolean value
```

### 5. `readByte()`
**`Java.io.RandomAccessFile.readByte()`** 从文件中读取一个有符号的八位值，从文件指针开始读取。

```java
Syntax :
public final byte readByte()
Parameters : 
-------
Return  :
signed eight-bit value from file
```

### 6. `readChar()`
**`Java.io.RandomAccessFile.readChar()`** 从文件中读取一个字符，从文件指针开始读取。

```java
Syntax :
public final char readChar()
Parameters : 
-------
Return  :
character from the file.
```

### 7. `readDouble()`
**`Java.io.RandomAccessFile.readDouble()`** 从文件中读取一个双精度值，从 File Pointer 开始读取。

```java
Syntax :
public final double readDouble()
Parameters : 
------
Return  :
reads a double value from the file.
```

### 8. `readFloat()`
**`Java.io.RandomAccessFile.readFloat()`** 从文件中读取一个浮点值，从文件指针开始读取。

```java
Syntax :
public final double readFloat()
Parameters : 
------
Return  :
reads a float value from the file.
```

### 9. `readFully(byte[] b)`
**`Java.io.RandomAccessFile.readFully(byte[] b)`** 从缓冲区读取 `b.length` 以下的字节，从文件指针开始读取。

```java
Syntax :
public final void readFully(byte[] b)
Parameters : 
b : buffer to be read
Return  :
reads bytes initialising from offset position upto b.length from the buffer
```

### 10. `readInt()`
**`Java.io.RandomAccessFile.readInt()`** 从文件中读取一个带符号的 4 字节整数，从 File Pointer 开始读取。

```java
Syntax :
public final int readInt()
Parameters : 
-----
Return  :
reads a signed 4 bytes integer from the file
```

### 11. `readFully(byte[] b, int offset, int len)`
**`Java.io.RandomAccessFile.readFully(byte[] b, int offset, int len)`** 从缓冲区读取从偏移量位置到 `b.length` 的初始化字节，从文件指针开始读取。

```java
Syntax :
public final void readFully(byte[] b, int offset, int len)
Parameters : 
b : buffer to read
offset : starting position to read
len : max no of bytes to read
Return  :
bytes initialising from offset position upto b.length from the buffer
```

### 12. `readLong()`
**`Java.io.RandomAccessFile.readLong()`** 从文件中读取一个带符号的 64 位整数，从 File Pointer 开始读取。

```java
Syntax :
public final long readLong()
Parameters : 
-------
Return  :
signed 64 bit integer from the file
```

```java
// Java Program illustrating use of io.RandomAccessFile class methods
// read(), read(byte[] b), readBoolean(), readByte(), readInt()
// readFully(byte[] b, int off, int len), readFully(), readFloat()
// readChar(), readDouble(),

import java.io.*;
public class NewClass
{
    public static void main(String[] args)
    {
        try
        {
            double d = 1.5;
            float f = 14.56f;

            // Creating a new RandomAccessFile - "GEEK"
            RandomAccessFile geek = new RandomAccessFile("GEEK.txt", "rw");

            // Writing to file
            geek.writeUTF("Hello Geeks For Geeks");

            // File Pointer at index position - 0
            geek.seek(0);

            // read() method :
            System.out.println("Use of read() method : " + geek.read());

            geek.seek(0);

            byte[] b = {1, 2, 3};

            // Use of .read(byte[] b) method :
            System.out.println("Use of .read(byte[] b) : " + geek.read(b));

            // readBoolean() method :
            System.out.println("Use of readBoolean() : " + geek.readBoolean());

            // readByte() method :
            System.out.println("Use of readByte() : " + geek.readByte());

            geek.writeChar('c');
            geek.seek(0);

            // readChar() :
            System.out.println("Use of readChar() : " + geek.readChar());

            geek.seek(0);
            geek.writeDouble(d);
            geek.seek(0);

            // read double
            System.out.println("Use of readDouble() : " + geek.readDouble());

            geek.seek(0);
            geek.writeFloat(f);
            geek.seek(0);

            // readFloat() :
            System.out.println("Use of readFloat() : " + geek.readFloat());

            geek.seek(0);
            // Create array upto geek.length
            byte[] arr = new byte[(int) geek.length()];
            // readFully() :
            geek.readFully(arr);

            String str1 = new String(arr);
            System.out.println("Use of readFully() : " + str1);

            geek.seek(0);

            // readFully(byte[] b, int off, int len) :
            geek.readFully(arr, 0, 8);

            String str2 = new String(arr);
            System.out.println("Use of readFully(byte[] b, int off, int len) : " + str2);
        }
        catch (IOException ex)
        {
            System.out.println("Something went Wrong");
            ex.printStackTrace();
        }
    }
}
```

**输出：**

```
Use of read() method : 0
Use of .read(byte[] b) : 3
Use of readBoolean() : true
Use of readByte() : 108
Use of readChar() : c
Use of readDouble() : 1.5
Use of readFloat() : 14.56
Use of readFully() : Geeks For Geeks
Use of readFully(byte[] b, int off, int len) : Geeks For Geeks
```

**下一个：** [第二集](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-2/) [第三集](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-3/)

本文由 **MohitGupta_OMG** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。