# Java 中的 AtomicInteger getAndDecrement() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomicinteger-getanddecrement-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-getanddecrement-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicInteger.getAndDecrement()` 是 Java 中的一个内置方法，它将给定值减少 1，并在更新前返回数据类型为 `int` 的值。

## 语法

```java
public final int getAndDecrement()
```

## 参数

该函数不接受任何参数。

## 返回值

该函数将执行减量操作前的值返回到前一个值。

## 示例程序

下面的程序演示了该功能：

### 程序 1

```java
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicInteger val = new AtomicInteger(0);

        // Decreases and gets the previous value
        int res = val.getAndDecrement();

        // Prints the updated value
        System.out.println("Previous value: " + res);
        System.out.println("Current value: " + val);
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
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 18
        AtomicInteger val = new AtomicInteger(18);

        // Decreases 1 and gets the previous value
        int res = val.getAndDecrement();

        // Prints the updated value
        System.out.println("Previous value: " + res);
        System.out.println("Current value: " + val);
    }
}
```

**输出：**

```java
Previous value: 18
Current value: 17
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#getAndDecrement--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#getAndDecrement--)