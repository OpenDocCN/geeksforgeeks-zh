# Java 中的 Hijrah 年表 `zonedDateTime()` 方法，示例：设置 1

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-zoneddatetime-method-in-java-with-example-set-1/](https://www.geeksforgeeks.org/hijrahchronology-zoneddatetime-method-in-java-with-example-set-1/)

`java.time.chrono.HijrahChronology` 类的 `zonedDateTime()` 方法用于根据伊斯兰回历从特定时刻检索特定区域的日期和时间。

## 语法

```java
public ChronoZonedDateTime zonedDateTime(Instant instant,
                                         ZoneId zone)
```

## 参数

该方法以下列参数为参数。

*   `instant`：`Instant` 类型的对象。
*   `zone`：`ZoneId` 类型的对象。

## 返回值

该方法根据伊斯兰回历从特定时刻返回特定区域的日期和时间。

以下是说明 `zonedDateTime()` 方法的示例：

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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting HijrahDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<HijrahDate> date
                = crono.zonedDateTime(
                    Instant.now(),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("HijrahDate and time is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
HijrahDate and time is: Hijrah-umalqura AH 1441-06-18T13:10:48.843Z[Etc/UTC]
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
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting HijrahDate and time for the
            // given Instant and ZoneId
            // by using zonedDateTime() method
            ChronoZonedDateTime<HijrahDate> date
                = crono.zonedDateTime(
                    Instant.ofEpochSecond(25000),
                    ZoneId.systemDefault());

            // display the result
            System.out.println("HijrahDate and time is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
HijrahDate and time is: Hijrah-umalqura AH 1389-10-22T06:56:40Z[Etc/UTC]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#zonedDateTime-java.time.Instant-java.time.ZoneId-)