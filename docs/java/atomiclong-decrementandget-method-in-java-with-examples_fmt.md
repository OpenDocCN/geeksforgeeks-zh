# Java 中的 AtomicLong decrementAndGet() 方法示例

> 原文：[https://www.geeksforgeeks.org/atomiclong-decrementandget-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclong-decrementandget-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLong.decrementAndGet()` 是 Java 中的一个内置方法，它将以前的值减少一，并在更新后返回数据类型为 `long` 的值。

**语法：**

```java
public final long decrementAndGet()
```

**参数：** 函数不接受单个参数。
**返回值：** 该函数将执行减量操作后的值返回到前一个值。

下面的程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the decrementAndGet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        System.out.println("Previous value: "
                           + val);

        // Decrement and get
        long res = val.decrementAndGet();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**输出：**

```java
Previous value: 0
Current value: -1
```

### 程序 2

```java
// Java program that demonstrates
// the decrementAndGet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        System.out.println("Previous value: "
                           + val);

        // Decrement and get new value
        long res = val.decrementAndGet();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**输出：**

```java
Previous value: 18
Current value: 17
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#decrementAndGet--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#decrementAndGet--)