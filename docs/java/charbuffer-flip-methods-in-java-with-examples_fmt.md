# Java 中的 CharBuffer flip()方法，示例

> 原文: [https://www.geeksforgeeks.org/charbuffer-flip-methods-in-java-with-examples/](https://www.geeksforgeeks.org/charbuffer-flip-methods-in-java-with-examples/)

[`java.nio.CharBuffer`](https://www.geeksforgeeks.org/tag/java-charbuffer/) 类的 [`flip()`](https://www.geeksforgeeks.org/tag/java-charbuffer/) 方法用于翻转该缓冲区。极限被设置为当前位置，然后位置被设置为零。如果标记被定义，那么它被丢弃。在一系列通道读取或放置操作之后，调用此方法为一系列通道写入或相关的获取操作做准备。

**例如:**

```java
buf.put(magic); // 前置表头
in.read(buf); // 将数据读入缓冲区的剩余部分
buf.flip(); // 翻转缓冲区
out.write(buf); // 将标题+数据写入通道
```

当从一个地方向另一个地方传输数据时，此方法通常与 [`compact()`](https://www.geeksforgeeks.org/tag/java-charbuffer/) 方法结合使用。

## 语法

```java
public final CharBuffer flip()
```

**返回值:** 这个方法返回这个缓冲区。

下面是一些示例来说明 [`flip()`](https://www.geeksforgeeks.org/tag/java-charbuffer/) 方法:

## 示例 1

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declare and initialize the char array
        char[] cb = { 'a', 'b', 'c' };

        // wrap the char array into CharBuffer
        // using wrap() method
        CharBuffer charBuffer
            = CharBuffer.wrap(cb);

        // set position at index 1
        charBuffer.position(1);

        // print the char buffer
        System.out.println("CharBuffer before flip: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // Flip the charBuffer
        // using flip() method
        charBuffer.flip();

        // print the byte buffer
        System.out.println("\nCharBuffer after flip: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
CharBuffer before flip: [a, b, c]
Position: 1
Limit: 3

CharBuffer after flip: [a, b, c]
Position: 0
Limit: 1
```

## 示例 2

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer
            = CharBuffer.allocate(4);

        // append char value in charBuffer
        // using append() method
        charBuffer.append('a');
        charBuffer.append('b');

        // print the char buffer
        System.out.println("CharBuffer before flip: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // Flip the charBuffer
        // using flip() method
        charBuffer.flip();

        // print the char buffer
        System.out.println("CharBuffer before flip: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
CharBuffer before flip: [a, b, c,  ]
Position: 3
Limit: 4
CharBuffer before flip: [a, b, c,  ]
Position: 0
Limit: 3
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#flip--](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#flip--)