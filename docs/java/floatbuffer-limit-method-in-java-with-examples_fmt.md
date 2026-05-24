# Java 中的 FloatBuffer limit()方法，带示例

> 原文: [https://www.geeksforgeeks.org/floatbuffer-limit-method-in-java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-limit-method-in-java-with-examples/)

[`java.nio.FloatBuffer`](https://www.geeksforgeeks.org/tag/java-floatbuffer/) 类的 `limit()` 方法用于修改该 `FloatBuffer` 的限制。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

## 语法

```java
public final FloatBuffer limit(int newLimit)
```

## 参数

该方法取整数型的一个参数 `newLimit`，该参数是指要设置为缓冲区新极限的极限。

## 返回值

该方法将指定的新限制设置为该缓冲区的新限制后，返回该缓冲区。

以下示例说明了 `limit()` 方法:

## 示例

### 示例 1

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(4);

        // put float value in FloatBuffer
        // using put() method
        floatBuffer.put(20.5f);
        floatBuffer.put(30.5f);

        // print the float buffer
        System.out.println(
            "FloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Limit the floatBuffer
        // using limit() method
        floatBuffer.limit(1);

        // print the float buffer
        System.out.println(
            "\nFloatBuffer after "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**输出:**

```
FloatBuffer before setting buffer's limit: [20.5, 30.5, 0.0, 0.0]
Position: 2
Limit: 4

FloatBuffer after setting buffer's limit: [20.5, 30.5, 0.0, 0.0]
Position: 1
Limit: 1
```

### 示例 2

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(5);

        // put float value in FloatBuffer
        // using put() method
        floatBuffer.put(20.5f);
        floatBuffer.put(30.5f);
        floatBuffer.put(40.5f);

        // mark will be going to
        // discarded by limit()
        floatBuffer.mark();

        // print the float buffer
        System.out.println(
            "FloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Limit the floatBuffer
        // using limit() method
        floatBuffer.limit(4);

        // print the double buffer
        System.out.println(
            "\nFloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**输出:**

```
FloatBuffer before setting buffer's limit: [20.5, 30.5, 40.5, 0.0, 0.0]
Position: 3
Limit: 5

FloatBuffer before setting buffer's limit: [20.5, 30.5, 40.5, 0.0, 0.0]
Position: 3
Limit: 4
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#limit-int-)