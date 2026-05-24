# Java中的AtomicLong longValue()方法

> 原文：[https://www.geeksforgeeks.org/atomiclong-longvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/atomiclong-longvalue-method-in-java-with-examples/)

`java.util.concurrent.atomic.AtomicLong.longValue()`是Java中的一个内置方法，它返回当前存储在对象中的值，并且它的数据类型为`long`。

## 语法

```java
public long longValue()
```

## 参数
该函数不接受任何参数。

## 返回值
该函数以`long`数据类型返回当前值。

下面的程序说明了上述方法：

## 程序1

```java
// Java program that demonstrates
// the longValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        long res = val.longValue();

        // Prints the updated value
        System.out.println("Current value: " + res);
    }
}
```

## 输出

```java
Current value: 0
```

## 程序2

```java
// Java program that demonstrates
// the longValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {
        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        long res = val.longValue();

        // Prints the updated value
        System.out.println("Current value: " + res);
    }
}
```

## 输出

```java
Current value: 18
```

## 参考
[https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#longValue--](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#longValue--)