# Java 中的 JapaneseChronology.zonedDateTime(Instant, ZoneId) 方法，示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-zoneddatetimeinstant-zoneid-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-zoneddatetimeinstant-zoneid-method-in-java-with-example/)

`Java.time.chrono.JapaneseChronology` 类的 `zonedDateTime()` 方法用于根据特定时刻的日历检索特定区域的日期和时间。

## 语法

```java
public ZonedDateTime zonedDateTime(
       Instant instant, ZoneId zone)
```

## 参数

该方法以下列参数为参数。

*   `Instant instant`：表示瞬间时间点。
*   `ZoneId zone`：表示时区。

## 返回值

该方法根据日本日历从特定时刻返回特定区域的区域日期时间。

以下是说明 `zonedDateTime()` 方法的示例：

## 示例 1

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<JapaneseDate> date
                = crono.zonedDateTime(
                    Instant.now(),
                    ZoneId.systemDefault());

            // display the result
            System.out.println(
                "JapaneseDate and time is: "
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

## 输出

```java
JapaneseDate and time is:
 Japanese Heisei 32-03-15T06:55:36.135Z[Etc/UTC]
```

## 示例 2

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<JapaneseDate> date
                = crono.zonedDateTime(
                    Instant.ofEpochSecond(25000),
                    ZoneId.systemDefault());

            // display the result
            System.out.println(
                "JapaneseDate and time is: "
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

## 输出

```java
JapaneseDate and time is:
 Japanese Showa 45-01-01T06:56:40Z[Etc/UTC]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-)