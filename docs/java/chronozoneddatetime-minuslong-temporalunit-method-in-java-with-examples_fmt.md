# Java 中的 ChronoZonedDateTime minus(long, TemporalUnit) 方法，示例

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-minuslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-minuslong-temporalunit-method-in-java-with-examples/)

`minus()` 方法的一个 `ChronoZonedDateTime` 接口用来返回这个日期时间的一个副本，减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

## 语法

```java
default ChronoZonedDateTime minus(long amountToSubtract,
                           TemporalUnit unit)
```

## 参数

此方法接受两个参数：

*   `amountToSubtract`：是要减去的单位数量，可以是一个负数。
*   `unit`：是要减去的单位。

## 返回值

该方法根据该日期时间，减去指定的金额，返回 `ChronoZonedDateTime`。

## 异常

此方法抛出以下异常：

*   `DateTimeException`：如果减法无法执行。
*   `UnsupportedTemporalTypeException`：如果该单位不被支持。
*   `ArithmeticException`：如果发生数值溢出。

下面的程序说明了 `minus()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.minus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // subtract 30 Months to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.minus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " subtracting Months:\n "
                           + value);
    }
}
```

## 输出

```java
ChronoZonedDateTime after subtracting Months:
 2016-06-06T19:21:12.123+05:30[Asia/Calcutta]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#minus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#minus-long-java.time.temporal.TemporalUnit-)