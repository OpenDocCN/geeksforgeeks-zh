# Java 中 of 方法的 LocalDateTime 示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-ofmonth-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofmonth-method-in-java-with-examples/)

## `of(int year, Month month, int dayOfMonth, int hour, int minute)` 方法

`LocalDateTime` 类中的 `of(int year, Month month, int dayOfMonth, int hour, int minute)` 方法用于根据输入的年、月、日、时、分创建 `LocalDateTime` 实例。该实例同时表示日期和时间。参数 `year`、`month` 和 `day` 用于确定日期，参数 `hour` 和 `minute` 用于确定时间。秒和纳秒将默认设置为零。

### 语法

```java
public static LocalDateTime of(int year,
                               Month month,
                               int dayOfMonth,
                               int hour,
                               int minute)
```

### 参数

该方法接受 5 个参数：

*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – `Month` 类型，代表一年中的月份。范围从一月到十二月。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。

### 返回值

该方法返回从输入值导出的 `LocalDateTime`。

### 异常

如果任何字段的值超出上述范围或者月中的某一天对于月-年无效，则该方法抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, Month month, int dayOfMonth, int hour, int minute)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2020, Month.MAY, 13, 6, 30);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

**输出**

```
DateTime: 2020-05-13T06:30
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2019, Month.MAY,
                13, 6, 30);

        // print month only
        System.out.println(
            "Month: "
            + localdatetime.getMonth());
    }
}
```

**输出**

```
Month: MAY
```

## `of(int year, Month month, int dayOfMonth, int hour, int minute, int second)` 方法

`LocalDateTime` 类中的 `of(int year, Month month, int dayOfMonth, int hour, int minute, int second)` 方法用于根据输入的年、月、日、时、分、秒创建 `LocalDateTime` 实例。创建实例时纳秒默认设置为零。在此方法中，只有月份作为 `Month` 实例传递，其他参数均为整数。此方法适用于不需要纳秒的场景。

### 语法

```java
public static LocalDateTime of(int year,
                               Month month,
                               int dayOfMonth,
                               int hour,
                               int minute,
                               int second)
```

### 参数

该方法接受六个参数：

*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – `Month` 类型，代表一年中的月份。范围从一月到十二月。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。
*   `second` – 整数型，表示分钟的秒。范围从 0 到 59。

### 返回值

该方法返回 `LocalDateTime`。

### 异常

如果任何字段的值超出范围或月日对于月年无效，此方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, Month month, int dayOfMonth, int hour, int minute, int second)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute,
// int second) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2020, Month.MAY, 13,
                6, 30, 45);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

**输出**

```
DateTime: 2020-05-13T06:30:45
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute,
// int second) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(2019, Month.MAY,
                               13, 6, 30, 45);

        // print year only
        System.out.println(
            "Year: "
            + localdatetime.getYear());
    }
}
```

**输出**

```
Year: 2019
```

## `of(int year, Month month, int dayOfMonth, int hour, int minute, int second, int nanoSecond)` 方法

`LocalDateTime` 类中的 `of(int year, Month month, int dayOfMonth, int hour, int minute, int second, int nanoSecond)` 方法用于根据输入的年、月、日、时、分、秒、纳秒创建 `LocalDateTime` 实例。该实例同时表示日期和时间。参数 `year`、`month` 和 `day` 用于确定日期，参数 `hour`、`minute`、`second` 和 `nanosecond` 用于确定时间。

### 语法

```java
public static LocalDateTime of(int year,
                               Month month,
                               int dayOfMonth,
                               int hour,
                               int minute,
                               int second,
                               int nanoOfSecond)
```

### 参数

该方法接受七个参数：

*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – `Month` 类型，代表一年中的月份。范围从一月到十二月。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。
*   `second` – 整数类型，表示分钟的秒。范围从 0 到 59。
*   `nanoOfSecond` – 整数型，代表秒的纳秒。范围从 0 到 999999999。

### 返回值

该方法返回 `LocalDateTime`。

### 异常

如果任何字段的值超出范围或月日对于月年无效，此方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, Month month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute,
// int second, int nanoOfSecond) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2020, Month.MAY, 13, 6,
                30, 45, 20000);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

**输出**

```
DateTime: 2020-05-13T06:30:45.000020
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, Month month,
// int dayOfMonth, int hour, int minute,
// int second, int nanoOfSecond) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2019, Month.DECEMBER, 31, 12,
                30, 45, 50000);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

**输出**

```
DateTime: 2019-12-31T12:30:45.000050
```

**参考文献**

1.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int))
2.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int))
3.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int, int))