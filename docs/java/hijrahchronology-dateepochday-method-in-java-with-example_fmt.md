# Java 中的 `HijrahChronology` `dateEpochDay()` 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-dateepochday-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-dateepochday-method-in-java-with-example/)

`java.time.chrono.HijrahChronology` 类的 `dateEpochDay()` 方法用于从大纪元日根据 Hijrah 日历系统获取本地日期。

**语法：**

```java
public HijrahDate dateEpochDay(long epochDay)
```

**参数：** 该方法以 `long` 类型的 `epochDay` 为参数。
**返回值：** 该方法从另一个 `TemporalAccessor` 对象返回根据 Hijrah 日历系统的本地日期。
**异常：** 如果给定的纪元日无法形成结构化日期，该方法抛出 `DateTimeException`。

以下是举例说明 `dateEpochDay()` 方法：

## 示例 1

```java
// Java program to demonstrate
// dateEpochDay() method

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

            // display the result
            System.out.println("current HijrahDate is: "
                               + hidate);

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nHijrahDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
current HijrahDate is: Hijrah-umalqura AH 1442-11-15

HijrahDate(according to ephochday) is: Hijrah-umalqura AH 1456-01-01
```

## 示例 2

```java
// Java program to demonstrate
// dateEpochDay() method

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

            // display the result
            System.out.println("current HijrahDate is: "
                               + hidate);

            // getting HijrahDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(234568);

            // display the result
            System.out.println("HijrahDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("\npassed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
current HijrahDate is: Hijrah-umalqura AH 1442-11-15

passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Hijrah date out of range
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateEpochDay-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateEpochDay-long-)