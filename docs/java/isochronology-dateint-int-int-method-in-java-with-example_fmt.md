# Java 中的 IsoChronology.date(int, int, int) 方法示例

> 原文: [https://www.geeksforgeeks.org/isochronology-dateint-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-dateint-int-int-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `date()` 方法用于根据 ISO 日历系统获取给定年、月和日的 `LocalDate`。

## 语法

```java
public LocalDate date(int prolepticYear,
                      int month,
                      int dayOfMonth)
```

## 参数

该方法以下列参数为参数。

*   `prolepticYear`: ISO 年份字段的整数预测年
*   `month`: ISO 月字段的整数月
*   `dayOfMonth`: ISO 日字段的整数日

## 返回值

该方法根据 ISO 日历系统返回给定年、月、日的 `LocalDate`。

## 异常

如果给定的日、月、年字段无法形成结构化日期，该方法抛出 `DateTimeException`。

以下举例说明 `date()` 方法：

### 示例 1

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
            // creating and initializing LocalDate Object
            LocalDate lodate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = lodate.getChronology();

            // getting LocalDate for the
            // given date, month and year field
            // by using date() method
            LocalDate date = crono.date(1440, 05, 24);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
LocalDate is: 1440-05-24
```

### 示例 2

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
            // creating and initializing LocalDate Object
            LocalDate lodate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = lodate.getChronology();

            // getting LocalDate for the
            // given date, month and year field
            // by using date() method
            LocalDate date = crono.date(2020, 05, 34);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid value for DayOfMonth (valid values 1 - 28/31): 34
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#date-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#date-int-int-int-)