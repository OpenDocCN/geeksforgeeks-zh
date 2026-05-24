# Java 中的 Hijrah 年表 `dateYearDay()` 方法，示例：第 2 集

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-dateyearday-method-in-java-with-example-set-2/](https://www.geeksforgeeks.org/hijrahchronology-dateyearday-method-in-java-with-example-set-2/)

`java.time.chrono.HijrahChronology` 类的 `dateYearDay()` 方法用于根据特定时代的伊斯兰回历检索 `LocalDate`。

## 语法
```java
public HijrahDate dateYearDay(Era era,
                              int year,
                              int day)
```

## 参数
该方法接受以下参数：
*   `era`：时代类型。
*   `year`：伊斯兰历年份。
*   `day`：伊斯兰历日字段的整数日。

## 返回值
该方法根据特定时代的伊斯兰回历返回 `LocalDate`。

## 异常
如果给定的日、月、年字段不能形成结构化的日期，该方法抛出 `DateTimeException`。

以下是说明 `dateYearDay()` 方法的例子：

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahDate for the
            // given date and year field
            // by using dateYearDay() method
            HijrahDate date
                = crono.dateYearDay(
                    HijrahEra.AH, 1440, 24);

            // display the result
            System.out.println("HijrahDate is: "
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

### 输出
```java
HijrahDate is: Hijrah-umalqura AH 1440-01-24
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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // getting HijrahDate for the
            // given date and year field
            // by using dateYearDay() method
            HijrahDate date
                = crono.dateYearDay(
                    HijrahEra.AH, 2019, 24);

            // display the result
            System.out.println("HijrahDate is: "
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

### 输出
```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid Hijrah date, year: 2019, month: 1
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateYearDay-java.time.chrono.Era-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateYearDay-java.time.chrono.Era-int-int-)