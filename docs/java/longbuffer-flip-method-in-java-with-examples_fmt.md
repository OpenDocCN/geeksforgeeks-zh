# Java 中的 LongBuffer flip()方法，带示例

> 原文: [https://www.geeksforgeeks.org/longbuffer-flip-method-in-java-with-examples/](https://www.geeksforgeeks.org/longbuffer-flip-method-in-java-with-examples/)

[`java.nio.LongBuffer`](https://www.geeksforgeeks.org/tag/java-longbuffer/) 类的 [`flip()`](https://www.geeksforgeeks.org/tag/java-longbuffer/) 方法用于翻转该缓冲区。翻转该缓冲区意味着

*   缓冲区将被修剪到当前位置。
*   然后位置将被更改为零。
*   如果缓冲区上有任何标记，该标记将被自动丢弃。

## 语法

```java
public final LongBuffer flip()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回翻转后的 [`LongBuffer`](https://www.geeksforgeeks.org/tag/java-longbuffer/) 实例。

下面是一些示例来说明 [`flip()`](https://www.geeksforgeeks.org/tag/java-longbuffer/) 方法:

### 示例 1

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// Declare and initialize
        // the long array
        long[] db
            = { 10, 20, 30 };

// wrap the long array
        // into LongBuffer
        // using wrap() method
        LongBuffer longBuffer
            = LongBuffer.wrap(db);

// set position at index 1
        longBuffer.position(1);

// print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

// Flip the Buffer
        // using flip() method
        longBuffer.flip();

// print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [10, 20, 30]
Position: 1
Limit: 3

Buffer after flip: [10, 20, 30]
Position: 0
Limit: 1
```

### 示例 2

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

// defining and allocating LongBuffer
        // using allocate() method
        LongBuffer longBuffer
            = LongBuffer.allocate(4);

// put long value in LongBuffer
        // using put() method
        longBuffer.put(20);
        longBuffer.put(34);

// set position at index 1
        longBuffer.position(1);

// print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

// Flip the Buffer
        // using flip() method
        longBuffer.flip();

// print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [20, 34, 0, 0]
Position: 1
Limit: 4

Buffer after flip: [20, 34, 0, 0]
Position: 0
Limit: 1
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/nio/LongBuffer.html#mark--](https://docs.oracle.com/javase/9/docs/api/java/nio/LongBuffer.html#mark--)