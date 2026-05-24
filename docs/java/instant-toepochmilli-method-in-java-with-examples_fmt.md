# Java 中的 Instant toEpochMilli() 方法

> 原文：[https://www.geeksforgeeks.org/instant-toepochmilli-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-toepochmilli-method-in-java-with-examples/)

`Instant` 类的 `toEpochMilli()` 方法用于将此瞬间转换为从 1970-01-01T00:00:00Z 的历元开始计算的毫秒数。此方法返回一个 `long` 类型的值。

## 语法

```java
public long toEpochMilli()
```

## 返回值

此方法返回自 1970-01-01T00:00:00Z 纪元以来的毫秒数。

## 异常

如果出现数值溢出，此方法将抛出 `ArithmeticException`。

以下程序说明了 `Instant.toEpochMilli()` 方法：

### 程序 1

```java
// Java program to demonstrate
// Instant.toEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get millisecond value using toEpochMilli()
        long value = instant.toEpochMilli();

        // print result
        System.out.println("Millisecond value: "
                           + value);
    }
}
```

![](img/042dbb230dbb2e9d4a7420975066b9cd.png)

### 程序 2

```java
// Java program to demonstrate
// Instant.toEpochMilli() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current Instant: "
                           + instant);

        // get millisecond value using toEpochMilli()
        long value = instant.toEpochMilli();

        // print result
        System.out.println("Millisecond value: "
                           + value);
    }
}
```

![](img/d127c41fdd848880375224fdaeeceba0.png)

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#toEpochMilli()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#toEpochMilli())