# Java中的`java.nio.IntBuffer`类

> 原文：[`https://www.geeksforgeks.org/java-nio-intbuffer-class-in-java/`](https://www.geeksforgeks.org/java-nio-intbuffer-class-in-java/)

**输入缓冲区**保存输入输出操作中使用的整数值序列。`IntBuffer`类在长缓冲区上提供以下四类操作：
*   读取单个整数的绝对和相对`get`方法。
*   写单整数的绝对和相对`put`方法。
*   相对大容量`put`和`get`方法，用于将`int`数组或其他`int`缓冲区中的连续`int`序列传输到该缓冲区中，并从该缓冲区传输到数组中。

`IntBuffer`可以通过以下方式创建：
*   `allocate()`：这为缓冲区的内容分配空间。
*   `wrap()`：这将现有的长数组包装到缓冲区中。

`IntBuffer`类的大多数方法都直接类似于`ByteBuffer`定义的方法。

## 类别声明

```java
public abstract class IntBuffer
    extends Buffer
    implements Comparable<IntBuffer>
```

## `IntBuffer`类的方法

| 方法 | 描述 |
| --- | --- |
| [`allocate(int capacity)`](https://www.geeksforgeks.org/intbuffer-allocate-method-in-java/) | 这个方法分配一个新的`int`缓冲区。 |
| [`array()`](https://www.geeksforgeks.org/intbuffer-array-method-in-java/) | 此方法返回支持此缓冲区的`int`数组。 |
| [`arrayOffset()`](https://www.geeksforgeks.org/intbuffer-arrayoffset-method-in-java/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| [`asReadOnlyBuffer()`](https://www.geeksforgeks.org/intbuffer-asreadonlybuffer-method-in-java/) | 此方法创建一个新的只读`int`缓冲区，共享该缓冲区的内容。 |
| [`compact()`](https://www.geeksforgeks.org/intbuffer-compact-method-in-java/) | 这个方法压缩这个缓冲区。 |
| [`compareTo(IntBuffer)`](https://www.geeksforgeks.org/intbuffer-compareto-method-in-java/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| [`duplicate()`](https://www.geeksforgeks.org/intbuffer-duplicate-method-in-java-with-examples/) | 此方法创建一个新的`int`缓冲区，共享该缓冲区的内容。 |
| [`equals(Object ob)`](https://www.geeksforgeks.org/intbuffer-equals-method-in-java/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| [`get()`](https://www.geeksforgeks.org/intbuffer-get-methods-in-java-set-1/) | 此方法是一个相对`get`方法，返回缓冲区当前位置的`int`。 |
| [`get(int index)`](https://www.geeksforgeks.org/intbuffer-get-methods-in-java-set-1/) | 此方法是绝对`get`方法，并返回给定索引处的`int`。 |
| [`get(int[] dst)`](https://www.geeksforgeks.org/intbuffer-get-methods-in-java-set-1/) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| [`get(int[] dst, int offset, int length)`](https://www.geeksforgeks.org/intbuffer-get-methods-in-java-set-1/) | 此方法相对于批量获取方法，并返回此缓冲区。 |
| [`hasArray()`](https://www.geeksforgeks.org/intbuffer-hasarray-method-in-java/) | 此方法告知此缓冲区是否由可访问的`int`数组支持。 |
| [`hashCode()`](https://www.geeksforgeks.org/intbuffer-hashcode-method-in-java/) | 此方法返回此缓冲区的当前哈希代码。 |
| [`isDirect()`](https://www.geeksforgeks.org/intbuffer-ismethod-in-java/) | 这个方法告诉这个`int`缓冲区是否是直接的。 |
| [`order()`](https://www.geeksforgeks.org/intbuffer-order-method-in-java/) | 此方法检索此缓冲区的字节顺序。 |
| [`put(int i)`](https://www.geeksforgeks.org/intbuffer-put-methods-in-java-set-1/) | 这个方法是一个相对`put`方法，返回这个缓冲区。 |
| [`put(int[] src)`](https://www.geeksforgeks.org/intbuffer-put-methods-in-java-set-1/) | 这个方法是一个相对大容量的`put`方法，并返回这个缓冲区。 |
| [`put(int[] src, int offset, int length)`](https://www.geeksforgeks.org/intbuffer-put-methods-in-java-set-1/) | 这个方法是一个相对大容量的`put`方法，并返回这个缓冲区。 |
| [`put(IntBuffer src)`](https://www.geeksforgeks.org/intbuffer-put-methods-in-java-set-1/) | 这个方法是一个相对大容量的`put`方法，并返回这个缓冲区。 |
| [`put(int index, int i)`](https://www.geeksforgeks.org/intbuffer-put-methods-in-java-set-1/) | 这个方法是一个绝对的大容量放入方法，并返回这个缓冲区。 |
| [`slice()`](https://www.geeksforgeks.org/intbuffer-slice-method-in-java/) | 此方法创建一个新的`int`缓冲区，其内容是该缓冲区内容的共享子序列。 |
| [`toString()`](https://www.geeksforgeks.org/intbuffer-tostring-method-in-java/) | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| [`wrap(int[] array)`](https://www.geeksforgeks.org/intbuffer-wrap-method-in-java/) | 此方法将`int`数组包装到缓冲区中。 |
| [`wrap(int[] array, int offset, int length)`](https://www.geeksforgeks.org/intbuffer-wrap-method-in-java/) | 此方法将`int`数组包装到缓冲区中。 |

## 示例程序

下面是一些演示`IntBuffer`类及其方法的程序：

### 例1

```java
// Java program to demonstrate
// IntBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declaring the capacity of the IntBuffer
        int Capacity = 10;

        // Creating the IntBuffer
        // creating object of intbuffer
        // and allocating size capacity
        IntBuffer ib = IntBuffer.allocate(Capacity);

        // putting the value in intbuffer
        ib.put(100);
        ib.put(2, 9);

        System.out.println("IntBuffer: "
                           + Arrays.toString(ib.array()));
    }
}
```

**输出**

```java
IntBuffer: [100, 0, 9, 0, 0, 0, 0, 0, 0, 0]
```

### 例2

```java
// Java program to demonstrate
// IntBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declaring the capacity of the IntBuffer
        int capacity = 10;

        // Creating the IntBuffer
        try {
            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(4);
            ib.put(2, 9);
            ib.rewind();

            // checking IntBuffer ib is backed by array or
            // not
            boolean isArray = ib.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("IntBuffer ib is"
                                   + " backed by array");
            else
                System.out.println(
                    "IntBuffer ib is"
                    + " not backed by any array");
        }

        catch (IllegalArgumentException e) {
            System.out.println(
                "IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println(
                "ReadOnlyBufferException catched");
        }
    }
}
```

**输出**

```java
IntBuffer ib is backed by array
```