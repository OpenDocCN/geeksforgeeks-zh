# Java 中的 MinguoChronology zonedDateTime(Instant, ZoneId) 方法

> 原文: [https://www.geeksforgeeks.org/minguochronology-zoneddatetimeinstant-zoneid-method-in-java/](https://www.geeksforgeeks.org/minguochronology-zoneddatetimeinstant-zoneid-method-in-java/)

`java.time.chrono.MinguoChronology` 类的 `zonedDateTime()` 方法用于根据特定时刻的 Minguo 日历检索特定区域的日期和时间。

## 语法

```java
public ZonedDateTime zonedDateTime(
       Instant instant, ZoneId zone)
```

## 参数

该方法以下列参数为参数。

*   `Instant instant`: 表示瞬间时间点。
*   `ZoneId zone`: 表示时区的对象。

## 返回值

该方法根据特定时刻的 Minguo 日历，返回特定区域的 `ZonedDateTime`。

以下是说明 `zonedDateTime()` 方法的示例：

### 例 1

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

            // getting MinguoDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<MinguoDate> date
                = crono.zonedDateTime(
                    Instant.now(),
                    ZoneId.systemDefault());

            // display the result
            System.out.println(
                "MinguoDate and time is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
MinguoDate and time is: Minguo ROC 109-04-20T14:24:49.696Z[Etc/UTC]
```

### 例 2

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

            // getting MinguoDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<MinguoDate> date
                = crono.zonedDateTime(
                    Instant.ofEpochSecond(25000),
                    ZoneId.systemDefault());

            // display the result
            System.out.println(
                "MinguoDate and time is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
MinguoDate and time is: Minguo ROC 59-01-01T06:56:40Z[Etc/UTC]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-)