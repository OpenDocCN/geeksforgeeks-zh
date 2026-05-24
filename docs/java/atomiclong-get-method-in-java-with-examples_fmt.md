# Java中的AtomicLong get()方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomiclong-get-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclong-get-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLong.get()`是Java中的一个内置方法，它返回`long`类型的当前值。

## 语法

```java
public final long get()
```

## 参数

该函数不接受任何参数。

## 返回值

该函数返回当前值。

下面的程序说明了上述方法：

### 程序 1

```java
// Java program that demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Gets the current value
        long res = val.get();

        System.out.println("current value: "
                           + res);
    }
}
```

**输出：**

```java
Previous value: 7
current value: 7
```

### 程序 2

```java
// Java program that demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Gets the current value
        long res = val.get();

        System.out.println("current value: "
                           + res);
    }
}
```

**输出：**

```java
Previous value: 25
current value: 25
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#get--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#get--)