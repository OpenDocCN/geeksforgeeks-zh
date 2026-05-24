# Java 中的 GregorianCalendar getGreatestMinimum() 方法

> 原文：[https://www.geeksforgeeks.org/gregoriancalendar-getgreatestminimum-method-in-java/](https://www.geeksforgeeks.org/gregoriancalendar-getgreatestminimum-method-in-java/)

`java.util.GregorianCalendar.getGreatestMinimum()` 方法是 Java 中的内置函数，它返回日历字段的最高最小值，作为参数传递给此 `GregorianCalendar` 实例的函数。任何可能的时间值的最高最小值被定义为 `get` 方法返回的最小值，同时考虑了 `getFirstDayOfWeek`、`getMinimalDaysInFirstWeek`、`getGregorianChange` 和 `getTimeZone` 方法的当前值。

## 语法

```java
public int getGreatestMinimum(int calendarField)
```

## 参数

该函数接受一个整数类型的强制参数 `calendarField`，该函数将返回其最高最小值。

## 返回值

该方法返回一个 `int`，表示指定日历字段的最高最小值。

## 示例

```java
Input : DAY_OF_MONTH
Output : 1

Input : WEEK_OF_MONTH
Output : 0
```

下面的程序说明了 `java.util.GregorianCalendar.getGreatestMinimum()` 函数的工作原理：

### 程序 1

```java
// Java Program to illustrate getGreatestMinimum()

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args) {

        // Create a new calendar
        GregorianCalendar cal = (GregorianCalendar)
            GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + cal.getTime());

        // Greatest minimum for WEEK_OF_MONTH
        int minm = cal.getGreatestMinimum(
            GregorianCalendar.WEEK_OF_MONTH);
        System.out.println("Greatest Minimum for"
                           + " WEEK_OF_MONTH field :" + minm);

        // Get greatest minimum for DAY_OF_MONTH
        minm = cal.getGreatestMinimum(
            GregorianCalendar.DAY_OF_MONTH);
        System.out.println("Greatest Minimum for"
                           + " DAY_OF_MONTH field:" + minm);
    }
}
```

### 输出

```java
Current Date and Time : Wed Aug 01 07:21:14 UTC 2018
Greatest Minimum for WEEK_OF_MONTH field :0
Greatest Minimum for DAY_OF_MONTH field:1
```

### 程序 2

```java
// Java Program to illustrate getGreatestMinimum()

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args) {

        // Create a new calendar
        GregorianCalendar cal = (GregorianCalendar)
            GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + cal.getTime());

        // Get greatest minimum for YEAR
        int minm = cal.getGreatestMinimum(
            GregorianCalendar.YEAR);
        System.out.println("Greatest Minimum for"
                           + " YEAR field :" + minm);

        // Get greatest minimum for HOUR_OF_DAY
        minm = cal.getGreatestMinimum(
            GregorianCalendar.HOUR_OF_DAY);
        System.out.println("Greatest Minimum for"
                           + " HOUR_OF_DAY field:" + minm);
    }
}
```

### 输出

```java
Current Date and Time : Wed Aug 01 07:21:16 UTC 2018
Greatest Minimum for YEAR field :1
Greatest Minimum for HOUR_OF_DAY field:0
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getMinimum()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getMinimum())