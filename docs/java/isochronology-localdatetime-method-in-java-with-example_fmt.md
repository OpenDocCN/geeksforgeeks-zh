# Java 中的 IsoChronology.localDateTime() 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-localdatetime-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-localdatetime-method-in-java-with-example/)

`Java.time.chrono.IsoChronology` 类的 `localDateTime()` 方法用于根据 ISO 日历系统从任何其他 `TemporalAccessor` 对象中检索 `LocalDateTime`。

## 语法

```java
public LocalDateTime localDateTime(TemporalAccessor temporal)
```

## 参数

该方法以任意 `TemporalAccessor` 对象为参数。

## 返回值

该方法根据 ISO 日历系统从 `TemporalAccessor` 对象返回 `LocalDateTime`。

以下是说明 `localDateTime()` 方法的示例：

## 示例 1

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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting LocalDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            LocalDateTime date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("LocalDateTime is: "
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
LocalDateTime is: 2018-10-25T23:12:31.123
```

## 示例 2

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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting LocalDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            LocalDateTime date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("LocalDateTime is: "
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
LocalDateTime is: 2018-12-30T19:34:50.630
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#localDateTime-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)