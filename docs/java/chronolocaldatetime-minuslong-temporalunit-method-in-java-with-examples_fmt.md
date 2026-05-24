# Java 中的 ChronoLocalDateTime minus(long, TemporalUnit) 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-minuslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-minuslong-temporalunit-method-in-java-with-examples/)

`ChronoLocalDateTime` 接口的 `minus()` 方法用于返回该日期时间的副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

## 语法

```java
default ChronoLocalDateTime<D> minus(long amountToSubtract, 
                                 TemporalUnit unit)
```

## 参数

该方法接受两个参数：
- `amountToSubtract`：要减去的金额，可以为负数。
- `unit`：要减去的量的单位，不能为 `null`。

## 返回值

该方法返回一个减去指定金额后的 `ChronoLocalDateTime`。

## 异常

此方法抛出以下异常：
- `DateTimeException` - 如果减法无法执行。
- `ArithmeticException` - 如果发生数值溢出。

下面的程序说明了 `minus()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.minus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ChronoLocalDateTime instance
        ChronoLocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation
        // of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // subtract 200 DAYS to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.minus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("ChronoLocalDateTime after"
                           + " subtracting DAYS: "
                           + value);
    }
}
```

## 输出

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after subtracting DAYS: 2019-06-14T19:15:30
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-long-java.time.temporal.TemporalUnit-)