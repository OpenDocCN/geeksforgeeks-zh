# Java 中的 Java.util.GregorianCalendar 类

> 原文: [https://www.geeksforgeeks.org/java-util-gregoriancalendar-class-java/](https://www.geeksforgeeks.org/java-util-gregoriancalendar-class-java/)

**先决条件:** [`java.util.Locale`](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/) 、 [`java.util.TimeZone`](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/) 、[`Calendar.get()`](https://www.geeksforgeeks.org/calendar-get-method-in-java/)

`GregorianCalendar` 是 `Calendar` 的一个具体子类（其所有继承成员的实现都来自接口或抽象类），该子类实现了我们所熟悉的最广泛使用的公历。

## Java.util.GregorianCalendar vs Java.util.Calendar

`GregorianCalendar` 和 `Calendar` 类的主要区别在于 `Calendar` 类是抽象类，不能实例化。因此 `Calendar` 类的一个对象被初始化为：

```java
Calendar cal = Calendar.getInstance();
```

这里，一个名为 `cal` 的 `Calendar` 类对象被初始化为默认区域和时区中的当前日期和时间。然而，`GregorianCalendar` 类是一个具体的类，可以被实例化。因此 `GregorianCalendar` 类的一个对象被初始化为：

```java
GregorianCalendar gcal = new GregorianCalendar();
```

这里，一个名为 `gcal` 的 `GregorianCalendar` 类对象被初始化为默认区域和时区中的当前日期和时间。

**字段定义:**

`GregorianCalendar` 类定义了两个字段：
- `AD`： 指公元（***anno Domini***）
- `BC`： 指公元前（Before Christ）

**构造函数:**
有多个用于 `GregorianCalendar` 对象的构造函数。广义上来说，`GregorianCalendar` 的构造函数要么在默认区域和时区中用用户指定的日期和/或时间初始化对象，要么在用户指定的区域和/或时区中用默认的日期和时间初始化对象。这些措施如下：

| **构造函数签名** | **描述** |
| --- | --- |
| `GregorianCalendar()` | 使用默认区域设置和时区中的当前日期和时间初始化对象 |
| `GregorianCalendar(int year, int month, int dayOfMonth)` | 使用在默认区域设置和时区中作为参数传递的日期集初始化对象 |
| `GregorianCalendar(int year, int month, int dayOfMonth, int hour, int minute)` | 使用在默认区域设置和时区中作为参数传递的日期和时间集初始化对象 |
| `GregorianCalendar(int year, int month, int dayOfMonth, int hour, int minute, int second)` | 使用在默认区域设置和时区中作为参数传递的日期和更具体的时间集初始化对象 |
| `GregorianCalendar(Locale locale)` | 使用默认时区中的当前日期和时间以及作为参数传递的区域设置初始化对象 |
| `GregorianCalendar(TimeZone timezone)` | 使用默认区域设置中的当前日期和时间以及作为参数传递的时区初始化对象 |
| `GregorianCalendar(TimeZone timezone, Locale locale)` | 使用区域设置中的当前日期和时间以及作为参数传递的时区初始化对象 |

方法 `from()`、`toZonedDateTime()` 在 JDK 8 中引入。

## 示例

### 示例 1：默认实例化对比

```java
// Java Program to show that Calendar class with
// default instantiation and GregorianCalendar class
// with default constructor is basically the same as both
// return the Gregorian Calendar for the default
// date, time, time zone and locale

import java.util.Calendar;
import java.util.GregorianCalendar;

class CalendarGFG {
    public static void main(String[] args)
    {
        // Creating an object of Calendar Class
        Calendar cal = Calendar.getInstance();

        /* Creating an object of
             GregorianCalendar Class */
        GregorianCalendar gcal = new GregorianCalendar();

        /* Displaying Current Date using
             Calendar Class */
        System.out.println("Calendar date: "
                           + cal.getTime());

        /* Displaying Current Date using
             GregorianCalendar Class */
        System.out.print("Gregorian date: "
                         + gcal.getTime());
    } // end of main function
} // end of class
```

**输出:**

```java
Calendar date: Sat Apr 28 13:36:37 UTC 2018
Gregorian date: Sat Apr 28 13:36:37 UTC 2018
```

### 示例 2：演示各种构造函数的用法

#### 1. 使用默认构造函数

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.Locale;
import java.util.TimeZone;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarGFG {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of GregorianCalendar class
             using default constructor*/
        GregorianCalendar gcal = new GregorianCalendar();

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: " + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: "
                         + Locale.getDefault().getDisplayName());
    } // end of main function
} // end of class
```

**输出:**

```java
Date: Apr 30, 2018
Time: 10:21:51 PM
Time Zone: Coordinated Universal Time
Locale: English (United States)
```

#### 2. 以年、月、日为参数

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.Locale;
import java.util.TimeZone;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarGFG {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of GregorianCalendar class
           by specifying year, month and dayOfMonth */
        GregorianCalendar gcal = new GregorianCalendar(2018, 3, 30);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: " + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: "
                         + Locale.getDefault().getDisplayName());
    } // end of main function
} // end of class
```

**输出:**

```java
Date: Apr 30, 2018
Time: 0:0:0 AM
Time Zone: Coordinated Universal Time
Locale: English (United States)
```

#### 3. 年、月、日、时、分

## Java 语言GregorianCalendar示例

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.Locale;
import java.util.TimeZone;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarGFG {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of GregorianCalendar class
           by specifying year, month, dayOfMonth,
           hourOfDay and minute */
        GregorianCalendar gcal = new GregorianCalendar(2018, 3, 30, 10, 21);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: " + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: "
                         + Locale.getDefault().getDisplayName());
    } // end of main function
} // end of class
```

**输出:**

```
Date: Apr 30, 2018
Time: 10:21:0 AM
Time Zone: Coordinated Universal Time
Locale: English (United States)
```

## 4. 通过年、月、日、月、时、分、秒

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.Locale;
import java.util.TimeZone;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarGFG {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of GregorianCalendar class
           by specifying year, month, dayOfMonth,
           hourOfDay, minute and second */
        GregorianCalendar gcal = new GregorianCalendar(2018, 3, 30, 10, 21, 51);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: " + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: "
                         + Locale.getDefault().getDisplayName());
    } // end of main function
} // end of class
```

**输出:**

```
Date: Apr 30, 2018
Time: 10:21:51 AM
Time Zone: Coordinated Universal Time
Locale: English (United States)
```

## 5. 通过将时区作为参数传递

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.TimeZone;
import java.util.Locale;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarTest {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of TimeZone class to create
             an object of GregorianCalendar class to assign
             an user defined time zone (GMT + 5:30)*/
        TimeZone tz = TimeZone.getTimeZone("GMT+5:30");
        GregorianCalendar gcal = new GregorianCalendar(tz);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: " + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: " + Locale.getDefault().getDisplayCountry());
    } // end of main function
} // end of class
```

**输出:**

```
Date: May 1, 2018
Time: 4:24:7 AM
Time Zone: GMT+05:30
Locale: United States
```

## 6. 通过将区域设置作为参数传递

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.TimeZone;
import java.util.Locale;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarTest {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of Locale class to create
             an object of GregorianCalendar class to assign
             an user defined locale (India)*/
        Locale l = new Locale("en", "IN");
        GregorianCalendar gcal = new GregorianCalendar(l);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: "
                         + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: " + l.getDisplayCountry());
    } // end of main function
} // end of class
```

**输出:**

```
Date: Apr 30, 2018
Time: 10:58:30 PM
Time Zone: Coordinated Universal Time
Locale: India
```

## 7. 通过将时区和区域设置作为参数传递

## Java 语言

```java
// Java program to demonstrate simple GregorianCalendar
// operations
import java.util.TimeZone;
import java.util.Locale;
import java.util.Calendar;
import java.util.GregorianCalendar;

public class GregorianCalendarTest {
    public static void main(String args[])
    {
        // declaring an array to store month abbreviations
        String month[] = { "Jan", "Feb", "Mar", "Apr",
                           "May", "Jun", "Jul", "Aug",
                           "Sep", "Oct", "Nov", "Dec" };

        // declaring an array to store AM or PM
        String amPm[] = { "AM", "PM" };

        /* Creating an object of TimeZone class and Locale
             class to create an object of GregorianCalendar
             class to assign an user defined time zone
             (GMT + 5:30) and locale (India)*/
        TimeZone tz = TimeZone.getTimeZone("GMT+5:30");
        Locale l = new Locale("en", "IN");
        GregorianCalendar gcal = new GregorianCalendar(tz, l);

        // displaying the date, time, time zone and locale
        System.out.print("Date: "
                         + month[gcal.get(Calendar.MONTH)] + " "
                         + gcal.get(Calendar.DATE) + ", "
                         + gcal.get(Calendar.YEAR) + "\n"
                         + "Time: "
                         + gcal.get(Calendar.HOUR) + ":"
                         + gcal.get(Calendar.MINUTE) + ":"
                         + gcal.get(Calendar.SECOND) + " "
                         + amPm[gcal.get(Calendar.AM_PM)] + "\n"
                         + "Time Zone: "
                         + gcal.getTimeZone().getDisplayName()
                         + "\n"
                         + "Locale: " + l.getDisplayCountry());
    } // end of main function
} // end of class
```

**输出:**

```java
Date: May 1, 2018
Time: 4:34:59 AM
Time Zone: GMT+05:30
Locale: India
```

**参考:**
[GregorianCalendar(Java 平台 SE 8)–甲骨文帮助中心](https://docs.oracle.com/javase/8/docs/api/java/util/GregorianCalendar.html)