# Java 中的 ChronoLocalDateTime plus(long, TemporalUnit)，带示例

> 原文：`https://www.geeksforgeeks.org/chronolocaldatetime-pluslong-temporalunit-in-java-with-examples/`

`ChronoLocalDateTime` 接口的 `plus()` 方法用于返回该日期时间的副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。

## 语法

```java
default ChronoLocalDateTime plus(long amountToSubtract, 
                                 TemporalUnit unit)
```

## 参数

该方法接受两个参数：`amountToSubtract`（可以为负数）和 `unit`（要相加金额的单位，不为空）。

## 返回值

该方法根据添加了指定金额的日期时间返回一个新的 `ChronoLocalDateTime`。

## 异常

该方法抛出以下异常：

*   `DateTimeException` – 如果无法添加
*   `ArithmeticException` – 如果出现数值溢出

下面的程序说明了 `plus()` 方法：

## 示例程序

```java
// Java program to demonstrate
// ChronoLocalDateTime.plus() method

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

        // Get the String representation of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // add 200 DAYS to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.plus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("ChronoLocalDateTime after adding DAYS: "
                           + value);
    }
}
```

**输出：**

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after adding DAYS: 2020-07-18T19:15:30
```

**参考：** `https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#plus-long-java.time.temporal.TemporalUnit-`