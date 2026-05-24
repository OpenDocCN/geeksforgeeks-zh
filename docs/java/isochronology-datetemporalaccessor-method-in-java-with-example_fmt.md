# Java 中的 IsoChronology date() 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-datetemporalaccessor-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-datetemporalaccessor-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `date()` 方法用于根据 ISO 系统从另一个 `TemporalAccessor` 对象获取 `LocalDate`。

## 语法

```java
public LocalDate date(TemporalAccessor temporal)
```

## 参数

该方法以任意 `TemporalAccessor` 的对象为参数。

## 返回值

该方法从另一个 `TemporalAccessor` 对象返回根据 Iso 日历系统的 `LocalDate`。

以下是说明 `date()` 方法的示例：

## 例 1

```java
// Java program to demonstrate
// date() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            LocalDate date = crono.date(zonedate);

            // display the result
            System.out.println("LocalDate is: " + date);
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
LocalDate is: 2018-10-25
```

## 例 2

```java
// Java program to demonstrate
// date() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // creating and initializing TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            LocalDate date = crono.date(localdate);

            // display the result
            System.out.println("LocalDate is: " + date);
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
LocalDate is: 2018-12-30
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#date-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#date-java.time.temporal.TemporalAccessor-)