# Java 中的 ChronoZonedDateTime range()方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-range-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-range-method-in-java-with-examples/)

`ChronoZonedDateTime` 接口的 `range()` 方法用于获取作为参数传递的字段的有效值范围。此方法返回 `ValueRange` 对象，该对象包含字段的最小和最大有效值。这个时区信息有助于提高返回范围的准确性。当字段不受支持并且方法无法返回范围值时，将引发异常。

## 语法

```java
default ValueRange range(TemporalField field)
```

## 参数

该方法接受一个单参数 `field`，该字段是获取取值范围的字段。

## 返回值

此方法返回 `ValueRange`，这是该字段的有效值范围，不为空。

## 异常

此方法抛出以下异常：

*   `DateTimeException` – 如果无法获取该字段的范围。
*   `UnsupportedTemporalTypeException` – 如果该字段不受支持。

下面的程序说明了 `range()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.range() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

        // get range of MILLI_OF_SECOND field
        // from ChronoZonedDateTime using range method
        ValueRange range
            = zonedDT.range(ChronoField.MILLI_OF_SECOND);

        // print range of MILLI_OF_SECOND
        System.out.println("Range of MILLI_OF_SECOND: "
                           + range);
    }
}
```

## 输出

```java
ChronoZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
Range of MILLI_OF_SECOND: 0 - 999
```

## 程序 2

```java
// Java program to demonstrate
// ChronoZonedDateTime.range() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

        // get range of NANO_OF_SECOND field
        // from zonedDateTime using range method
        ValueRange range
            = zonedDT.range(ChronoField.NANO_OF_SECOND);

        // print range of NANO_OF_SECOND
        System.out.println("Range of NANO_OF_SECOND: "
                           + range);
    }
}
```

## 输出

```java
ChronoZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
Range of NANO_OF_SECOND: 0 - 999999999
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#range-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#range-java.time.temporal.TemporalField-)