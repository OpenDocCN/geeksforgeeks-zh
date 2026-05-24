# Java 中的 JapaneseChronology localDateTime() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-localdatetime-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-localdatetime-method-in-java-with-example/)

`JapaneseChronology` 类的 `localDateTime()` 方法用于根据日本日历系统，从任何 `TemporalAccessor` 对象中检索本地日期和时间。

## 语法

```java
public ChronoLocalDateTime localDateTime(TemporalAccessor temporal)
```

## 参数

该方法以一个 `TemporalAccessor` 对象作为参数。

## 返回值

此方法根据日本日历系统，从给定的 `TemporalAccessor` 对象返回一个 `ChronoLocalDateTime`。

以下是说明 `localDateTime()` 方法的示例：

### 示例 1

```java
// Java program to demonstrate
// localDateTime() method

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

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("JapaneseDate is: "
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
JapaneseDate is: Japanese Heisei 30-10-25T23:12:31.123
```

### 示例 2

```java
// Java program to demonstrate
// localDateTime() method

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

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("JapaneseDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
JapaneseDate is: Japanese Heisei 30-12-30T19:34:50.630
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#localDateTime-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)