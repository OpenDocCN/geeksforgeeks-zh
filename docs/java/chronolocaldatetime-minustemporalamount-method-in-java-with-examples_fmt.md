# Java 中的 ChronoLocalDateTime minus(TemporalAmount)方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-minustemporalamount-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-minustemporalamount-method-in-java-with-examples/)

`ChronoLocalDateTime` 接口的 `minus()` 方法用于返回该日期时间的副本，其中指定的数量被减去。该数量通常为 `Period` 或 `Duration`，但也可以是实现 `TemporalAmount` 接口的任何其他类型。

## 语法

```java
default ChronoLocalDateTime minus(TemporalAmount amountToSubtract)
```

## 参数

此方法接受一个单参数 `amountToSubtract`，为要减去的量，不应为 `null`。

## 返回值

该方法基于该日期时间进行减法运算，返回 `ChronoLocalDateTime`，不为 `null`。

## 异常

此方法抛出以下异常：

*   `DateTimeException` – 如果无法进行减法运算
*   `ArithmeticException` – 如果出现数值溢出

## 示例

下面的程序说明了 `minus()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.minus() method

import java.time.*;
import java.time.chrono.*;

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

        // subtract 10 Days to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.minus(Period.ofDays(10));

        // print result
        System.out.println("ChronoLocalDateTime after"
                           + " subtracting Days: "
                           + value);
    }
}
```

### 输出

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after subtracting Days: 2019-12-21T19:15:30
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-java.time.temporal.TemporalAmount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#minus-java.time.temporal.TemporalAmount-)