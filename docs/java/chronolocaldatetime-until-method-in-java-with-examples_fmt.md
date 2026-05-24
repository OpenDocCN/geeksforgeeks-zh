# Java 中的 ChronoLocalDateTime until() 方法示例

> 原文: [https://www.geeksforgeeks.org/chronolocaldatetime-until-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-until-method-in-java-with-examples/)

`until()` 方法在 `ChronoLocalDateTime` 接口中用于计算两个 `ChronoLocalDateTime` 对象之间的时间量，使用指定的时间单位。开始点和结束点是这样的：指定的 `ChronoLocalDateTime` 作为参数传递。如果结束点在开始点之前，结果将为负数。该计算返回一个整数，表示两个 `ChronoLocalDateTime` 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

## 语法

```java
public long until(Temporal endExclusive, 
                  TemporalUnit unit)
```

## 参数

该方法接受两个参数：

*   `endExclusive` 是结束日期，不包括在内，它被转换为一个 `ChronoLocalDateTime`。
*   `unit` 是计量金额的单位。

## 返回值

该方法返回该时间点日期时间和结束时间点日期时间之间的 `时间量`。

## 异常

该方法抛出以下异常：

*   `DateTimeException` – 如果金额无法计算，或者结束时间无法转换为 `ChronoLocalDateTime`。
*   `UnsupportedTemporalTypeException` – 如果不支持该单位。
*   `ArithmeticException` – 如果出现数值溢出。

以下程序说明了 `until()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDateTime objects
        ChronoLocalDateTime z1
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        ChronoLocalDateTime z2
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

        // apply until method of ChronoLocalDateTime class
        long result
            = z1.until(z2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**Output:**

```java
Result in HOURS: -10364
```

## 程序 2

```java
// Java program to demonstrate
// ChronoLocalDateTime.until() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDateTime objects
        ChronoLocalDateTime z1
            = LocalDateTime
                  .parse("1999-10-31T19:15:30");

        ChronoLocalDateTime z2
            = LocalDateTime.parse(
                "1990-10-25T23:12:31.123");

        // apply until method of ChronoLocalDateTime class
        long result
            = z2.until(z1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**Output:**

```java
Result in DAYS: 3292
```

## 参考文献

[https://docs.oracle.com/javase/9/docs/api/java/time/temporal/Temporal.html#until-java.time.temporal.Temporal-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/Temporal.html#until-java.time.temporal.Temporal-java.time.temporal.TemporalUnit-)