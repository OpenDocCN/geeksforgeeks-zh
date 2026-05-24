# LongBuffer 在 Java 中的 put() 方法

> 原文: [https://www.geeksforgeeks.org/longbuffer-put-methods-in-java/](https://www.geeksforgeeks.org/longbuffer-put-methods-in-java/)

## put(Long i)

`LongBuffer` 类的 `put(Long i)` 方法用于将给定的 `Long` 值写入当前位置的 `LongBuffer`，然后递增该位置。

### 语法

```java
public abstract LongBuffer put(Long i)
```

### 参数

该方法以 `Long` 值 `i` 为参数，写入 `LongBuffer`。

### 返回值

此方法返回此缓冲区 (`this`)，其中已插入了 `Long` 值。

### 异常

此方法抛出以下异常：

*   `BufferOverflowException` - 如果此缓冲区的当前位置不小于其限制。
*   `ReadOnlyBufferException` - 如果此缓冲区是只读的。

下面是一些例子来说明 `put(Long i)` 方法：

### 示例 1

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer using put() method
            ib.put(8);
            ib.put(9);
            ib.put(7);
            ib.rewind();

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));
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
Original LongBuffer:  [8, 9, 7]
```

### 示例 2

演示 `BufferOverflowException`。

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer using put() method
            ib.put(8);
            ib.put(9);
            ib.put(7);

            System.out.println("Trying to put the Long at the "
                               + "position more than its limit");
            ib.put(7);

            // rewind the Longbuffer
            ib.rewind();

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));
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
Trying to put the Long at the position more than its limit
Exception throws : java.nio.BufferOverflowException
```

### 示例 3

演示 `ReadOnlyBufferException`。

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity using allocate() method
            LongBuffer ib = LongBuffer.allocate(capacity);

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer ib1 = ib.asReadOnlyBuffer();

            System.out.println("Trying to put the Long value"
                               + " in read only buffer");

            // putting the value in readonly Longbuffer
            // using put() method
            ib1.put(8);
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
Trying to put the Long value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException
```