# Java 中的 AtomicLong intValue()方法，带示例

> 原文：[https://www.geeksforgeeks.org/atomiclong-intvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclong-intvalue-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLong.intValue()` 是 Java 中的一个内置方法，它通过执行一个缩小的原语转换来返回当前存储在数据类型为 `long` 的对象中的值。

## 语法：
```java
public long intValue()
```

## 参数：
函数不接受单个参数。

## 返回值：
函数返回当前值。

下面的程序说明了上述方法：

## 程序 1：
```java
// Java program that demonstrates
// the intValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        long res = val.intValue();

        // Prints the updated value
        System.out.println("Current value: " + res);
    }
}
```

## 输出：
```java
Current value: 0
```

## 程序 2：
```java
// Java program that demonstrates
// the intValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        long res = val.intValue();

        // Prints the updated value
        System.out.println("Current value: " + res);
    }
}
```

## 输出：
```java
Current value: 18
```

## 参考：
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#intValue--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#intValue--)