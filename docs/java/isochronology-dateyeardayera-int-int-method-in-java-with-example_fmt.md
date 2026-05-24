# Java 中的 IsoChronology 的 dateYearDay(Era, int, int) 方法示例

> 原文: [https://www.geeksforgeeks.org/isochronology-dateyeardayera-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-dateyeardayera-int-int-method-in-java-with-example/)

`Java.time.chrono.IsoChronology` 类的 `dateYearDay()` 方法用于根据特定时代的 Iso 日历检索 `LocalDate`。

## 语法

```java
public LocalDate dateYearDay(Era era,
                             int yearOfEra,
                             int dayOfYear)
```

## 参数

该方法以下列参数为参数。

*   `Era`: 是时代类型。
*   `yearOfEra`: 是年份字段的整数年份。
*   `dayOfYear`: 是年份中的日字段的整数日。

## 返回值

该方法根据特定时代的 Iso 日历返回 `LocalDate`。

以下是举例说明 `dateYearDay()` 方法的例子:

## 例 1

```java
// Java program to demonstrate
// dateYearDay() method

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
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting LocalDate for the
            // given date and year field
            // by using dateYearDay() method
            LocalDate date
                = crono.dateYearDay(
                    IsoEra.BCE, 1440, 24);

            // display the result
            System.out.println("LocalDate is: "
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

## 输出

```java
LocalDate is: -1439-01-24
```

## 例 2

```java
// Java program to demonstrate
// dateYearDay() method

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
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting LocalDate for the
            // given date and year field
            // by using dateYearDay() method
            LocalDate date
                = crono.dateYearDay(
                    IsoEra.BCE, 0000, 30);

            // display the result
            System.out.println("LocalDate is: "
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

## 输出

```java
LocalDate is: 0001-01-30
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateYearDay-java.time.chrono.Era-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateYearDay-java.time.chrono.Era-int-int-)