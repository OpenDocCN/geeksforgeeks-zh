# Java 中 ChronoZonedDateTime 的 with(TemporalField, long) 方法及示例

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-withtemporalfield-long-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withtemporalfield-long-method-in-java-with-examples/)

`ChronoZonedDateTime` 接口的 `with(TemporalField field, long newValue)` 方法用于将时区日期时间的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年、日、月、小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。`ChronoZonedDateTime` 的实例是不可变的，不受此方法调用的影响。

## 语法

```java
ChronoZonedDateTime with(TemporalField field,
                         long newValue)
```

## 参数

该方法接受两个参数：
*   `field`：要在结果中设置的字段。
*   `newValue`：结果中该字段的新值。

## 返回值

该方法返回一个基于此 `ChronoZonedDateTime` 设置了指定字段的新实例。

## 异常

此方法抛出以下异常：
*   `DateTimeException` - 如果无法进行调整。
*   `UnsupportedTemporalTypeException` - 如果字段不受支持。
*   `ArithmeticException` - 如果发生数值溢出。

## 示例

下面的程序说明了 `with()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print instance
        System.out.println("ChronoZonedDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoZonedDateTime
        ChronoZonedDateTime updatedlocal
            = time.with(ChronoField.YEAR, 2017);

        // print instance
        System.out.println("ChronoZonedDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
ChronoZonedDateTime before adjustment: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime after adjustment: 2017-12-06T19:21:12.123+05:30[Asia/Calcutta]
```

### 程序 2

```java
// Java program to demonstrate
// ChronoZonedDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // print instance
        System.out.println("ChronoZonedDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoZonedDateTime
        ChronoZonedDateTime updatedlocal
            = time.with(ChronoField.MONTH_OF_YEAR, 1);

        // print instance
        System.out.println("ChronoZonedDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
ChronoZonedDateTime before adjustment: 1918-10-25T23:12:38.543Z[Europe/Paris]
ChronoZonedDateTime after adjustment: 1918-01-25T23:12:38.543Z[Europe/Paris]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#with-java.time.temporal.TemporalField-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#with-java.time.temporal.TemporalField-long-)