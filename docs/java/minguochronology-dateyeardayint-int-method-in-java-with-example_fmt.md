# Java 中的 Minguo 年表 `dateYearDay(int, int)` 方法示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-dateyeardayint-int-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateyeardayint-int-method-in-java-with-example/)

`java.time.chrono.MinguoChronology` 类的 `dateYearDay()` 方法用于根据特定年份和日期的 Minguo 日历检索本地日期。

## 语法

```java
public MinguoDate dateYearDay(int year,
                              int day)
```

## 参数

该方法以下列参数为参数：

*   `year`：是民国年字段的整数规划年
*   `day`：是 `MinguoDate` 的日字段的整数日

## 返回值

此方法根据特定年份和日期的 Minguo 日历返回 `MinguoDate`。

## 异常

如果给定的日、月、年字段不能形成结构化的日期，该方法抛出 `DateTimeException`。

以下是举例说明 `dateYearDay()` 方法的例子：

## 例 1

### 示例代码

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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date = crono.dateYearDay(1440, 24);

            // display the result
            System.out.println("MinguoDate is: " + date);
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
MinguoDate is: Minguo ROC 1440-01-24
```

## 例 2

### 示例代码

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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // getting MinguoDate for the
            // given date and year field
            // by using dateYearDay() method
            MinguoDate date = crono.dateYearDay(2019, -24);

            // display the result
            System.out.println("MinguoDate is: " + date);
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
Exception thrown:
 java.time.DateTimeException:
 Invalid value for DayOfYear
 (valid values 1 - 365/366): -24
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateYearDay-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateYearDay-int-int-)