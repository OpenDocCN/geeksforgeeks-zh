# Java 中的 MinguoChronology 日期(TemporalAccessor)方法，示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-datetemporalaccessor-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-datetemporalaccessor-method-in-java-with-example/)

`Java.time.chrono.MinguoChronology`类的`date()`方法用于根据 Minguo 日历系统从另一个 TemporalAccessor 对象获取本地日期。

## 语法

```java
public MinguoDate date(TemporalAccessor temporal)
```

## 参数

该方法以任意 TemporalAccessor 的对象为参数。

## 返回值

该方法从另一个 TemporalAccessor 对象返回根据民国日历系统的本地日期。

以下是说明`date()`方法的示例：

## 示例 1

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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using date() method
            MinguoDate date = crono.date(zonedate);

            // display the result
            System.out.println("MinguoDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

## 输出

```java
MinguoDate is: Minguo ROC 107-10-25
```

## 示例 2

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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting MinguoDate for the
            // given TemporalAccessor object
            // by using date() method
            MinguoDate date = crono.date(localdate);

            // display the result
            System.out.println("MinguoDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

## 输出

```java
MinguoDate is: Minguo ROC 107-12-30
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#date-java.time.chrono.Era-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#date-java.time.chrono.Era-int-int-int-)