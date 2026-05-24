# Java 中的 `FloatBuffer` 类

> 原文：[https://www.geeksforgeeks.org/java-nio-floatbuffer-class-in-java/](https://www.geeksforgeeks.org/java-nio-floatbuffer-class-in-java/)

缓冲区对象可以被称为固定数据量的容器。缓冲区充当存储箱或临时暂存区，在这里可以存储数据，并在以后根据使用情况进行检索。Java 缓冲类是构建 `java.nio` 的基础。`FloatBuffer` 是通过 `allocate()`（为缓冲区的内容分配空间）、将现有的浮点数组 `wrap()` 到缓冲区或创建现有 `ByteBuffer` 的视图来创建的。

这个类定义了 `FloatBuffer` 上的四类操作：
*   绝对和相对 `get()` 和 `put()` 方法读取和写入单个浮点数。
*   相对批量 `get()` 方法，将连续的浮点序列从该缓冲区传输到数组中。
*   相对批量 `put()` 方法，将连续的浮点序列从浮点数组或其他浮点缓冲区传输到该缓冲区。
*   压缩、复制和切片 `FloatBuffer` 的方法。

| 方法 | 描述 |
| --- | --- |
| `allocate(int capacity)` | 这个方法分配一个新的 `FloatBuffer`。 |
| `array()` | 此方法返回支持此缓冲区的浮点数组。 |
| `arrayOffset()` | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| `asReadOnlyBuffer()` | 此方法创建一个新的只读 `FloatBuffer`，共享该缓冲区的内容。 |
| `compact()` | 这个方法压缩这个缓冲区。 |
| `compareTo(FloatBuffer that)` | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| `duplicate()` | 此方法创建一个共享该缓冲区内容的新 `FloatBuffer`。 |
| `equals(Object ob)` | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| `get()` | 此方法是相对 `get()` 方法。 |
| `get(float[] dst)` | 此方法是相对批量获取方法。 |
| `get(float[] dst, int offset, int length)` | 此方法是相对批量获取方法。 |
| `get(int index)` | 这个方法是绝对 `get()` 方法。 |
| `hasArray()` | 此方法告知此缓冲区是否由可访问的浮点数组支持。 |
| `hashCode()` | 此方法返回此缓冲区的当前哈希码。 |
| `isDirect()` | 这个方法告诉这个 `FloatBuffer` 是否是直接的。 |
| `order()` | 此方法检索此缓冲区的字节顺序。 |
| `put(float f)` | 这种方法是相对 `put()` 方法。 |
| `put(float[] src)` | 这种方法是相对批量 `put()` 方法。 |
| `put(float[] src, int offset, int length)` | 这种方法是相对批量 `put()` 方法。 |
| `put(FloatBuffer src)` | 相对批量 `put()` 方法。 |
| `put(int index, float f)` | 绝对 `put()` 方法。 |
| `slice()` | 创建一个新的 `FloatBuffer`，其内容是该缓冲区内容的共享子序列。 |
| `toString()` | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| `wrap(float[] array)` | 此方法将浮点数组包装到缓冲区中。 |
| `wrap(float[] array, int offset, int length)` | 此方法将浮点数组包装到缓冲区中。 |

## 方法实现示例

下面是 `java.nio.FloatBuffer` 类的一些方法的实现：

### 1. `reset()`
此方法用于将此缓冲区的位置重置到之前标记的位置。

```java
Syntax: public final FloatBuffer reset()
Parameters: None
Return: Returns the buffer.
```

```java
// Implementation of reset() method in Java

import java.nio.*;
import java.util.*;

public class Example {

    public static void main(String[] args)
    {

        try {

            float[] arr = { 10.5f, 20.5f, 30.5f, 40.5f };

            // creating object of FloatBuffer
            // and allocating size capacity
            FloatBuffer x = FloatBuffer.wrap(arr);

            // try to set the position at index 2
            x.position(2);

            // Set this buffer mark position
            // using mark() method
            x.mark();

            // try to set the position at index 4
            x.position(4);

            // display position
            System.out.println("Pos before reset: "
                               + x.position());

            // try to call reset() to restore
            // to the position we marked
            x.reset();

            // display position
            System.out.println("Pos after reset: "
                               + x.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("New pos is less than "
                               + "the pos "
                               + " marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output**

```java
Pos before reset: 4
Pos after reset: 2
```

### 2. `rewind()`
这个方法用来倒带这个缓冲区。

```java
Syntax: public final FloatBuffer rewind()
Parameters: None
Return: Returns the buffer
```

```java
// Implementation of rewind() method in Java

import java.nio.*;
import java.util.*;

public class Example2 {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer x = FloatBuffer.allocate(4);

        // put char value in FloatBuffer
        // using put() method
        x.put(10.5f);
        x.put(20.5f);

        // print the float buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(x.array())
                           + "\nPosition: " + x.position()
                           + "\nLimit: " + x.limit());

        // rewind the Buffer
        // using rewind() method
        x.rewind();

        // print the floatbuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(x.array())
                           + "\nPosition: " + x.position()
                           + "\nLimit: " + x.limit());
    }
}
```

**Output**

```java
Buffer before operation: [10.5, 20.5, 0.0, 0.0]
Position: 2
Limit: 4

Buffer after operation: [10.5, 20.5, 0.0, 0.0]
Position: 0
Limit: 4
```