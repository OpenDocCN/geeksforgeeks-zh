# Java 中的 MinguoChronology zonedDateTime(TemporalAccessor) 方法

> 原文：[https://www.geeksforgeeks.org/minguochronology-zoneddatetimetemporalaccessor-method-in-java/](https://www.geeksforgeeks.org/minguochronology-zoneddatetimetemporalaccessor-method-in-java/)

`java.time.chrono.MinguoChronology` 类的 `zonedDateTime()` 方法用于从另一个 `TemporalAccessor` 对象获取根据民国历法系统的区域日期和时间。

## 语法

```java
public ZonedDateTime zonedDateTime(
          TemporalAccessor temporal)
```

## 参数

该方法以任意时态取值器的对象为参数。

## 返回值

该方法从另一个 `TemporalAccessor` 对象返回根据民国日历系统的分区日期和时间。

以下是说明 `zonedDateTime()` 方法的示例：

## 示例

### 示例 1

```java
// Java program to demonstrate
// zonedDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime
                      .parse(
                          "2018-10-25T23:12:31."
                          + "123+02:00[Europe/Paris]");

            // getting MinguoDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<MinguoDate> date
                = crono.zonedDateTime(zonedate);

            // display the result
            System.out.println(
                "MinguoDate and time is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
MinguoDate and time is:
 Minguo ROC 107-10-25T23:12:31.123+02:00[Europe/Paris]
```

### 示例 2

```java
// Java program to demonstrate
// zonedDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

            // getting MinguoDate and time for the
            // given TemporalAccessor object
            // by using zonedDateTime() method
            ChronoZonedDateTime<MinguoDate> date
                = crono.zonedDateTime(localdate);

            // display the result
            System.out.println(
                "MinguoDate and time is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 Unable to obtain ChronoZonedDateTime from TemporalAccessor:
 class java.time.LocalDateTime
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#zonedDateTime-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#zonedDateTime-java.time.temporal.TemporalAccessor-)