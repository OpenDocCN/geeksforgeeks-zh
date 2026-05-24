# Java 中的 GregorianCalendar getMaximum()方法

> 原文: [https://www.geeksforgeeks.org/gregoriancalendar-getmaximum-method-in-java/](https://www.geeksforgeeks.org/gregoriancalendar-getmaximum-method-in-java/)

`java.util.GregorianCalendar.getMaximum()`方法是 Java 中的内置函数，它返回作为参数传递给函数的特定日历字段的最大值。对于任何可能的时间值，它都是`get()`方法返回的最高值，同时考虑`getFirstDayOfWeek()`、`getMinimalDaysInFirstWeek()`、`getGregorianChange()`和`getTimeZone()`方法的当前值。

## 语法

```java
public int getMaximum(int calendarField)
```

## 参数

该函数接受一个强制参数`calendarField`，该参数的最大值`这个`日历日历字段实例将由该函数返回。

## 返回值

该方法返回`这个`公历实例的指定日历字段的最大值。

## 示例

```java
Input : DAY_OF_MONTH
Output : 31

Input : WEEK_OF_MONTH
Output : 6
```

下面的程序说明了`java.util.GregorianCalendar.getMaximum()`函数：

## 程序 1

```java
// Java Program to illustrate getMaximum() function

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar cal = (GregorianCalendar)
                         GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                                    + cal.getTime());

        // Display maximum for WEEK_OF_MONTH
        int maxm = cal.getMaximum
                   (GregorianCalendar.WEEK_OF_MONTH);
        System.out.println("Maximum for WEEK_OF_MONTH field :"
                                             + maxm);

        // Display maximum for DAY_OF_MONTH
        maxm = cal.getMaximum
                    (GregorianCalendar.DAY_OF_MONTH);
        System.out.println("Maximum for DAY_OF_MONTH field:"
                                            + maxm);
    }
}
```

## 输出

```java
Current Date and Time : Fri Jul 27 12:44:38 UTC 2018
Maximum for WEEK_OF_MONTH field :6
Maximum for DAY_OF_MONTH field:31
```

## 程序 2

```java
// Java Program to illustrate getMaximum() function

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar cal = (GregorianCalendar)
                      GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                       + cal.getTime());

        // Display maximum for YEAR
        int maxm = cal.getMaximum(GregorianCalendar.YEAR);
        System.out.println("Maximum for YEAR field :"
                       + maxm);

        // Display maximum for HOUR_OF_DAY
        maxm = cal.getMaximum(GregorianCalendar.HOUR_OF_DAY);
        System.out.println("Maximum for HOUR_OF_DAY field:"
                       + maxm);
    }
}
```

## 输出

```java
Current Date and Time : Fri Jul 27 12:44:40 UTC 2018
Maximum for YEAR field :292278994
Maximum for HOUR_OF_DAY field:23
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getMaximum(int)](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#getMaximum(int))