# java 中的 `java.nio.CharBuffer` 类

> 原文: [https://www.geeksforgeeks.org/java-nio-charbuffer-class-in-java/](https://www.geeksforgeeks.org/java-nio-charbuffer-class-in-java/)

**字符缓冲区**保存输入/输出操作中使用的整数值序列。 `CharBuffer` 类在长缓冲区上提供以下四类操作:

*   读取单个字符的绝对和相对获取方法。
*   写单个字符的绝对和相对 `put` 方法。
*   相对大容量放入和获取方法，用于将连续的字符序列从 `int` 数组或其他字符缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

短缓冲区可以通过以下方式创建:

*   `allocate()`: 这为缓冲区的内容分配空间。
*   `wrap()`: 这将现有的长数组包装到缓冲区中。

`CharBuffer` 类的大多数方法直接类似于 `ByteBuffer` 定义的方法。

**类别申报:**

> `public abstract class CharBuffer`
> `extends Buffer`
> `implements Comparable<CharBuffer>, Appendable, CharSequence, Readable`

**`CharBuffer` 类的方法:**

| 方法 | 描述 |
| --- | --- |
| `allocate(int capacity)` | 此方法分配一个新的字符缓冲区。 |
| `append(char c)` | 此方法将指定的字符追加到此缓冲区。 |
| `append(CharSequence csq)` | 此方法将指定的字符序列追加到此缓冲区。 |
| `append(CharSequence csq, int start, int end)` | 此方法将指定字符序列的子序列追加到此缓冲区 |
| `array()` | 此方法返回支持此缓冲区的 `char` 数组 |
| `arrayOffset()` | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量 |
| `asReadOnlyBuffer()` | 此方法创建一个新的只读字符缓冲区，共享该缓冲区的内容。 |
| `charAt(int index)` | 此方法读取相对于当前位置的给定索引处的字符。 |
| `compact()` | 这个方法压缩这个缓冲区 |
| `compareTo(CharBuffer)` | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| `duplicate()` | 此方法创建一个新的字符缓冲区，共享该缓冲区的内容。 |
| `equals(Object ob)` | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| `get()` | 此方法是一个相对 `get` 方法，返回 |
| `get(char[] dst)` | 此方法是相对批量获取方法，并返回 |
| `get(char[] dst, int offset, int length)` | 此方法是相对批量获取方法，并返回 |
| `get(int index)` | 此方法是绝对 `get` 方法，并返回 |
| `hasArray()` | 此方法告知此缓冲区是否由可访问的字符数组支持。 |
| `hashCode()` | 此方法返回此缓冲区的当前哈希代码。 |
| `isDirect()` | 这个方法告诉这个字符缓冲区是否是直接的。 |
| `length()` | 这个方法返回这个字符缓冲区的长度。 |
| `order()` | 此方法检索此缓冲区的字节顺序。 |
| `put(char c)` | 此方法是一个相对的 `put` 方法，返回 |
| `put(char[] src)` | 此方法是相对大容量的 `put` 方法，并返回 |
| `put(char[] src, int offset, int length)` | 此方法是相对大容量的 `put` 方法，并返回 |
| `put(CharBuffer src)` | 此方法是相对大容量的 `put` 方法，并返回 |
| `put(int index, char c)` | 此方法是绝对看跌方法，并返回 |
| `put(String src)` | 此方法是相对大容量的 `put` 方法，并返回 |
| `put(String src, int start, int end)` | 此方法是相对大容量的 `put` 方法，并返回 |
| `read(CharBuffer target)` | 此方法尝试将字符读入指定的字符缓冲区。 |
| `slice()` | 此方法创建一个新的字符缓冲区，其内容是该缓冲区内容的共享子序列。 |
| `subSequence(int start, int end)` | 此方法创建一个新的字符缓冲区，表示相对于当前位置的该缓冲区的指定子序列。 |
| `toString()` | 此方法返回包含此缓冲区中字符的字符串。 |
| `wrap(char[] array)` | 此方法将字符数组包装到缓冲区中。 |
| `wrap(char[] array, int offset, int length)` | 此方法将字符数组包装到缓冲区中。 |
| `wrap(CharSequence csq)` | 此方法将字符序列包装到缓冲区中。 |
| `wrap(CharSequence csq, int start, int end)` | 此方法将字符序列包装到缓冲区中。 |

**下面是一些演示 `CharBuffer` 类及其方法的程序:**

### 例 1:

```java
// Java program to demonstrate
// CharBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// Declaring the capacity of the CharBuffer
        char capacity = 10;

// Creating the CharBuffer

// creating object of Charbuffer
        // and allocating size capacity
        CharBuffer fb = CharBuffer.allocate(capacity);

// putting the value in charbuffer
        fb.put('a');
        fb.put(5, 'b');
          fb.put(7, 'c');

// Printing the CharBuffer
        System.out.println("ChartBuffer: "
                        + Arrays.toString(fb.array()));
    }
}
```

**输出:**

```java
ChartBuffer: [a, , , , , b, , c, , ]
```

### 例 2:

```java
// Java program to demonstrate
// CharBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// Declaring the capacity of the CharBuffer
        int capacity = 4;

// Creating the CharBuffer
        try {

// creating object of CharBuffer
            // and allocating size capacity
            CharBuffer charbuffer
                = CharBuffer.allocate(capacity);

// append the value in CharBuffer
            // using append() method
            charbuffer.append('a')
                .append('b')
                .append('c')
                  .append('d')
                .rewind();

// print the CharBuffer
            System.out.println("Original CharBuffer: "
                            + Arrays.toString(
                                    charbuffer.array()));
        }

catch (BufferOverflowException e) {

System.out.println("Exception throws : " + e);
        }

catch (ReadOnlyBufferException e) {

System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original CharBuffer: [a, b, c, d]
```