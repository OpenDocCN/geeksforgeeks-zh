# Java 中的 Minguo 年表 `date(int, int, int)` 方法示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-dateint-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-dateint-int-int-method-in-java-with-example/)

`java.time.chrono.MinguoChronology` 类的 `date()` 方法用于根据给定年、月、日的 Minguo 日历系统获取 `LocalDate`。

## 语法

```java
public MinguoDate date(int prolepticYear,
                       int month,
                       int dayOfMonth)
```

## 参数

该方法以下列参数为参数：

*   `prolepticYear`：Minguo 日期年份字段的整数预测年
*   `month`：`MinguoDate` 月字段的整数月
*   `dayOfMonth`：日字段为 `MinguoDate` 的整数日

## 返回值

该方法根据民国历法系统返回给定年、月、日的 `LocalDate`。

## 异常

如果给定的日、月、年字段无法形成结构化日期，该方法抛出 `DateTimeException`。

以下举例说明 `date()` 方法：

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
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoDate for the
            // given date, month and year field
            // by using date() mehtod
            MinguoDate date = crono.date(2040, 05, 24);

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

**输出：**

```java
MinguoDate is: Minguo ROC 2040-05-24
```