# java 中的 java.nio.ByteOrder 类

> 原文: [https://www.geeksforgeeks.org/java-nio-byteorder-class-in-java/](https://www.geeksforgeeks.org/java-nio-byteorder-class-in-java/)

`ByteOrder` 是一个来自 [java.nio 包](https://www.geeksforgeeks.org/introduction-to-java-nio-with-examples/)的类。一般来说，字节顺序意味着字节顺序的枚举。

*   在 java 中，有像 `int`、`char`、`float`、`double` 这样的原始数据类型，它们会将数据以一定的字节数存储在主内存中。
*   例如，字符或短整数占用 2 字节，32 位整数或浮点值占用 4 字节，长整数或双精度浮点值占用 8 字节。
*   这些多字节类型之一的每个值都存储在一系列连续的存储单元中。
*   这里，考虑一个占据 8 个字节的长整数，这 8 个字节可以存储在内存中(从低地址到高地址)为 13，17，21，25，29，34，38，42；这种排列方式被称为大端序(最高有效字节“大”端存储在最低地址)。
*   或者，这些字节可以存储为 42、38、34、29、25、21、17、13；这种排列被称为小端顺序(最低有效字节“小”端存储在最低地址到最高地址)。

> **注意:** `ByteOrder` 类扩展了 `Object` 类，它是类层次结构的根。

`ByteOrder` 类有两个字段

| 字段 | 描述 |
| --- | --- |
| `BIG_ENDIAN` | 这是一个指示大端字节顺序的字段。 |
| `LITTLE_ENDIAN` | 这是一个指示小端字节顺序的常量字段。 |

**语法:** 类声明

```java
public final class ByteOrder extends Object {}
```

这个类的方法如下:

| 方法 | 描述 |
| --- | --- |
| `nativeOrder()` | 这个方法被定义为通过向 JVM 分配相同顺序的直接缓冲区来提高 JVM 的性能。该方法返回运行该 Java 虚拟机的硬件的本机字节顺序。 |
| `toString()` | 此方法返回在指定方式中定义的字符串。 |

**实施:**

**例**

## Java 示例

```java
// Java Program to demonstrate ByteOrder Class

// Importing input output and utility classes
import java.io.*;

// Importing required classes from java.nio package
// for network linking
import java.nio.ByteBuffer;
import java.nio.ByteOrder;
import java.nio.IntBuffer;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Here object is created and allocated and
        // it with 8 bytes of memory
        ByteBuffer buf = ByteBuffer.allocate(8);

        // This line of code prints the os order
        System.out.println("OS Order         :- "
                           + ByteOrder.nativeOrder());

        // This line of code prints the ByteBuffer order
        // Saying that whether it is in BIG_ENDIAN or
        // LITTLE_ENDIAN
        System.out.println("ByteBuffer Order :- "
                           + buf.order());

        // Here the conversion of int to byte takes place
        buf.put(new byte[] { 13, 17, 21, 25 });

        // Setting the bit set to its complement using
        // flip() method of Java BitSet class
        buf.flip();

        IntBuffer integerbuffer = buf.asIntBuffer();

        System.out.println("{" + integerbuffer.position()
                           + " : " + integerbuffer.get()
                           + "}");

        integerbuffer.flip();

        buf.order(ByteOrder.LITTLE_ENDIAN);

        integerbuffer = buf.asIntBuffer();

        System.out.println("{" + integerbuffer.position()
                           + " : " + integerbuffer.get()
                           + "}");
    }
}
```

**输出**

```java
OS Order         :- LITTLE_ENDIAN
ByteBuffer Order :- BIG_ENDIAN
{0 : 219223321}
{0 : 420811021}
```

> **注:**
> *   新创建的字节缓冲区的顺序始终是 `BIG_ENDIAN`。
> *   不同的机器可以有不同的操作系统顺序。