# Java 中 ChronoLocalDateTime 接口的 with(TemporalField, long) 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-withtemporalfield-long-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-withtemporalfield-long-method-in-java-with-examples/)

`ChronoLocalDateTime` 接口的 `with(TemporalField field, long newValue)` 方法用于将日期时间的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年、日、月、小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。`ChronoLocalDateTime` 的这个实例是不可变的，不受此方法调用的影响。

## 语法

```java
ChronoLocalDateTime with(TemporalField field, long newValue)
```

## 参数

此方法接受两个参数：
- `field`：要在结果中设置的字段。
- `newValue`：结果中字段的新值。

## 返回值

该方法基于此 `ChronoLocalDateTime` 返回一个设置了指定字段的新实例。

## 异常

此方法抛出以下异常：
- `DateTimeException`：如果无法进行调整。
- `UnsupportedTemporalTypeException`：如果字段不受支持。
- `ArithmeticException`：如果发生数值溢出。

## 示例程序

下面的程序说明了 `with()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(ChronoField.YEAR, 2017);

        // print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
ChronoLocalDateTime before adjustment: 2019-12-31T19:15:30
ChronoLocalDateTime after adjustment: 2017-12-31T19:15:30
```

### 程序 2

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

        // apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(ChronoField.MONTH_OF_YEAR, 1);

        // print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
ChronoLocalDateTime before adjustment: 2018-10-25T23:12:31.123
ChronoLocalDateTime after adjustment: 2018-01-25T23:12:31.123
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#with-java.time.temporal.TemporalField-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#with-java.time.temporal.TemporalField-long-)