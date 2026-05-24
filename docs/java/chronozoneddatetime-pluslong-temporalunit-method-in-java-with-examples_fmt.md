# Java 中的 `ChronoZonedDateTime.plus(long, TemporalUnit)` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-pluslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-pluslong-temporalunit-method-in-java-with-examples/)

`plus()` 方法是 `ChronoZonedDateTime` 类的一个方法，用于返回这个日期时间的一个副本，并添加指定数量的单位。如果无法添加金额，因为不支持该单位或其他原因，则会引发异常。

## 语法

```java
default ChronoZonedDateTime plus(long amountToSubtract,
                           TemporalUnit unit)
```

## 参数

该方法接受两个参数：
*   `amountToSubtract`：是要添加到结果中的单位量，可能为负数。
*   `unit`：是要添加的量的单位。

## 返回值

该方法根据该日期时间返回 `ChronoZonedDateTime`，并添加指定的金额。

## 异常

该方法抛出以下异常：
*   `DateTimeException`：如果无法添加。
*   `UnsupportedTemporalTypeException`：如果不支持该单元。
*   `ArithmeticException`：如果出现数值溢出。

下面的程序说明了 `plus()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.plus() method

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

        // add 30 Months to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.plus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " adding Months:\n "
                           + value);
    }
}
```

### Output

```java
ChronoZonedDateTime after adding Months:
 2021-06-06T19:21:12.123+05:30[Asia/Calcutta]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#plus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#plus-long-java.time.temporal.TemporalUnit-)