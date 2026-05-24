# Java 中的 LongBuffer allocate() 方法

> 原文: [https://www.geeksforgeeks.org/longbuffer-allocate-method-in-java/](https://www.geeksforgeeks.org/longbuffer-allocate-method-in-java/)

`java.nio.LongBuffer` 类的 `allocate()` 方法用于在现有缓冲区旁边分配一个新的长缓冲区。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。

**语法:**

```java
public static LongBuffer allocate(Long capacity)
```

**参数:** 该方法以长整型新缓冲区的容量为参数。
**返回值:** 此方法返回新的长缓冲区。
**异常:** 如果容量为负数，此方法抛出 `IllegalArgumentException`。

以下程序说明了 `allocate()` 方法:

## 示例程序 1

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int Capacity = 10;

        // Creating the LongBuffer
        // creating object of Longbuffer
        // and allocating size capacity
        LongBuffer ib = LongBuffer.allocate(Capacity);

        // putting the value in Longbuffer
        ib.put(11);
        ib.put(2, 19);

        System.out.println("LongBuffer: "
                           + Arrays.toString(ib.array()));
    }
}
```

**输出:**

```java
LongBuffer: [11, 0, 19, 0, 0, 0, 0, 0, 0, 0]
```

## 示例程序 2: 演示非法容量异常

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        // by negative long
        int Capacity = -10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size with negative long
            System.out.println("Trying to allocate a Negative long");

            LongBuffer ib = LongBuffer.allocate(Capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
Trying to allocate a Negative long
Exception thrown: java.lang.IllegalArgumentException: capacity < 0: (-10 < 0)
```