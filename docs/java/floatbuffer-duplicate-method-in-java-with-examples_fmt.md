# Java 中的 FloatBuffer duplicate() 方法示例

> 原文：[https://www.geeksforgeeks.org/floatbuffer-duplicate-method-in-java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-duplicate-method-in-java-with-examples/)

`java.nio.FloatBuffer` 类的 `duplicate()` 方法用于创建共享给定缓冲区内容的新的 `FloatBuffer`。

新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲区的位置、极限和标记值将是独立的。

新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

## 语法

```java
public abstract FloatBuffer duplicate()
```

## 返回值

该方法返回新的 `FloatBuffer`，其携带以前的 `FloatBuffer` 内容。

以下是说明 `duplicate()` 方法的示例：

## 示例 1：使用直接 FloatBuffer

```java
// Java program to demonstrate
// duplicate() method
// Using direct floatbuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb1.put(8.56F);
            fb1.put(2, 9.61F);
            fb1.rewind();

            // print the Original FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb1.array()));

            // Creating a duplicate copy of FloatBuffer
            // using duplicate() method
            FloatBuffer fb2 = fb1.duplicate();

            // print the duplicate copy of FloatBuffer
            System.out.print("\nDuplicate FloatBuffer: "
                             + Arrays.toString(fb2.array()));
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**输出：**

```java
Original FloatBuffer:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

Duplicate FloatBuffer: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
```

## 示例 2：使用只读 FloatBuffer

```java
// Java program to demonstrate
// duplicate() method
// using read-only floatbuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb1.put(8.56F);
            fb1.put(2, 9.61F);
            fb1.rewind();

            // print the Original FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb1.array()));

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer readonly = fb1.asReadOnlyBuffer();

            // print the read-only copy of FloatBuffer
            System.out.print("\nread-only FloatBuffer:  ");
            while (readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");
            System.out.println("");

            // Rewinding the readonly FloatBuffer
            readonly.rewind();

            // Creating a duplicate copy of FloatBuffer
            // using duplicate() method
            FloatBuffer fb2 = readonly.duplicate();

            // print the duplicate copy of FloatBuffer
            System.out.print("\nduplicate copy of read-only FloatBuffer:  ");

            while (fb2.hasRemaining())
                System.out.print(fb2.get() + ", ");
            System.out.println("");
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**输出：**

```java
Original FloatBuffer:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

read-only FloatBuffer:  8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0,

duplicate copy of read-only FloatBuffer:  8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0,
```