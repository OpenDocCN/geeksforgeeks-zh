# java 中的 java.nio.Buffer 类

> 原文：[https://www.geeksforgeeks.org/java-nio-buffer-class-in-java/](https://www.geeksforgeeks.org/java-nio-buffer-class-in-java/)

`Buffer`类为特定原语类型的数据块提供了一个缓冲区或容器。元素的有限序列线性存储在缓冲器中。

方便在数据中执行读写操作的缓冲区的重要属性有：

*   **Capacity：** 此属性通过元素的索引确定缓冲区中可读写数据的限制。
*   **Limit：** 此属性通过元素的索引确定缓冲区中可读写数据的限制。
*   **Position：** 此属性确定缓冲区中当前元素的位置。

## 语法：类声明

```java
public abstract class Buffer extends Object
```

`Buffer`类为以下每个缓冲区数据类型提供了一个子类，如`ByteBuffer`、`MappedByteBuffer`、`CharBuffer`、`DoubleBuffer`、`FloatBuffer`、`IntBuffer`、`LongBuffer`、`ShortBuffer`。`Buffer`类从类`java.lang.Object`继承了以下方法，如`clone()`、`finalize()`、`getClass()`、`hashCode()`、`notifyAll()`、`toString()`、`wait()`。现在，我们继续讨论`Buffer`类的方法，如下所示，按字母顺序排列：

| 方法 | 描述 |
| --- | --- |
| `array()` | 此方法返回支持此缓冲区的数组 |
| `arrayOffset()` | 此方法返回缓冲区的第一个元素 |
| `capacity()` | 此方法返回此缓冲区的容量。 |
| `clear()` | 此方法清除此缓冲区。 |
| `flip()` | 这个方法翻转这个缓冲区。 |
| `hasArray()` | 这个方法告诉这个缓冲区是否由一个可访问的数组支持。 |
| `hasRemaining()` | 这个方法告诉当前位置和极限之间是否有元素。 |
| `isDirect()` | 这个方法告诉这个缓冲区是否是直接的。 |
| `isReadOnly()` | 这个方法告诉这个缓冲区是否是只读的。 |
| `limit()` | 这个方法返回这个缓冲区的限制。 |
| `limit(int newLimit)` | 这个方法设置这个缓冲区的限制。 |
| `mark()` | 此方法将此缓冲区的标记设置在其位置。 |
| `position()` | 这个方法返回这个缓冲区的位置。 |
| `position(int newPosition)` | 这个方法设置这个缓冲区的位置。 |
| `remaining()` | 此方法返回当前位置与极限之间的元素个数。 |
| `reset()` | 此方法将此缓冲区的位置重置为之前标记的位置。 |
| `rewind()` | 此方法倒带此缓冲区。 |

## 实现：缓冲类及其方法

### 例 1

```java
// Java program to demonstrate Buffer Class

// Importing required libraries
import java.nio.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // Try block to check for exceptions
        try {

            // Creating the ByteBuffer

            // Creating object of ByteBuffer class and
            // allocating size capacity
            ByteBuffer bufferObj
                = ByteBuffer.allocate(capacity);

            // Putting the int to byte typecast
            // value in ByteBuffer using put() method

            // Custom input entries
            bufferObj.put((byte)10);
            bufferObj.put((byte)20);
            bufferObj.put((byte)30);
            bufferObj.put((byte)40);
            bufferObj.put((byte)50);

            // Typecasting ByteBuffer into Buffer
            Buffer bufferObj1 = (Buffer)bufferObj;

            // Getting array that backs this buffer
            // using array() method
            byte[] arr = (byte[])bufferObj1.array();

            // Display message only
            System.out.print(" The array is : [");

            // Print the array
            for (int i = 0; i < arr.length; i++)
                System.out.print(" " + arr[i]);
            System.out.print(" ]");
        }

        // Catch block to handle the exception
        catch (ReadOnlyBufferException e) {

            // Print message where exception occurred
            // is displayed on console
            System.out.println("Exception throws: " + e);
        }
    }
}
```

### 输出

```java
 The array is : [ 10 20 30 40 50 ]
```

### 例 2

```java
// Java Program to illustrate
// remaining() method of Buffer Class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // Creating the ByteBuffer
        ByteBuffer bufferObj
            = ByteBuffer.allocate(capacity);

        // Checking the position
        System.out.println("The position of buffer"
                           + " is: "
                           + bufferObj.position());

        // Checking the limit
        System.out.println("The limit of buffer"
                           + " is: "
                           + bufferObj.limit());

        // Putting the int to byte typecast
        // value in ByteBuffer using put() method
        bufferObj.put((byte)10);
        bufferObj.put((byte)20);
        bufferObj.put((byte)30);

        // Checking the remaining using remaining()
        // method
        System.out.println("The number of "
                           + "remaining elements"
                           + " in buffer is: "
                           + bufferObj.remaining());
    }
}
```

### 输出

```java
The position of buffer is: 0
The limit of buffer is: 5
The number of remaining elements in buffer is: 2
```