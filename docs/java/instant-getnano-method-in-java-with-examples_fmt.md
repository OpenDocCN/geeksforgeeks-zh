# Java 中的 Instant getNano() 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-getnano-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-getnano-method-in-java-with-examples/)

`Instant` 类的 `getNano()` 方法用于返回此瞬间所代表的时间线上的纳秒数，从秒开始算起。它测量从 `getEpochSecond()` 返回的秒值开始的纳秒总数。

## 语法

```java
public int getNano()
```

## 返回值

该方法返回秒值内的纳秒部分，该值始终为正，且不超过 999,999,999。

下面的程序说明了 `getNano()` 方法：

## 程序 1

```java
// Java program to demonstrate
// Instant.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get nano second of second secondvalue
        // using getNano()
        int value = instant.getNano();

        // print result
        System.out.println("nanoseconds value: "
                           + value);
    }
}
```

**输出：**

```java
nanoseconds value: 630000000
```

## 程序 2

```java
// Java program to demonstrate
// Instant.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current Instant:"
                           + instant);

        // get nano second of second secondvalue
        // using getNano()
        int value = instant.getNano();

        // print result
        System.out.println("nanoseconds value: "
                           + value);
    }
}
```

**输出：**

```java
Current Instant:2018-11-27T04:21:27.029Z
nanoseconds value: 29000000
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#getNano()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#getNano())