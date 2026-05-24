# Java 中的 CharBuffer put()方法

> 原文：`https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/`

## put(char i)

`java.nio.CharBuffer` 类的 `put(char i)` 方法用于将给定字符写入当前位置新创建的 `CharBuffer`，然后增加位置。

**语法：**

```java
public abstract CharBuffer put(char i)
```

**参数：** 该方法将字符值 `i` 作为参数写入字符缓冲区。

**返回值：** 这个方法返回这个缓冲区，其中插入了字符值。

**异常：** 此方法抛出以下异常：

*   `BufferOverflowException` - 如果此缓冲区的当前位置不小于其限制。
*   `ReadOnlyBufferException` - 如果此缓冲区是只读的。

以下是举例说明 `put(char i)` 方法的例子：

### 示例 1

```java
// Java program to demonstrate
// put(char i) method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer using put() method
            cb.put('a');
            cb.put('b');
            cb.put('c');
            cb.rewind();

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));
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

**输出：**

```java
Original CharBuffer: [a, b, c]
```

### 示例 2：演示 BufferOverflowException

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer using put() method
            cb.put('a');
            cb.put('b');
            cb.put('c');

            System.out.println("Trying to put the Int at the "
                               + "position more than its limit");
            cb.put('d');

            // rewind the Charbuffer
            cb.rewind();

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));
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

**输出：**

```java
Trying to put the Int at the position more than its limit
Exception throws : java.nio.BufferOverflowException
```

### 示例 3：演示 ReadOnlyBufferException

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity using allocate() method
            CharBuffer cb = CharBuffer.allocate(capacity);

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer cb1 = cb.asReadOnlyBuffer();

            System.out.println("Trying to put the Int value"
                               + " in read only buffer");

            // putting the value in readonly Charbuffer
            // using put() method
            cb1.put('a');
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

**输出：**

```java
Trying to put the Int value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException
```