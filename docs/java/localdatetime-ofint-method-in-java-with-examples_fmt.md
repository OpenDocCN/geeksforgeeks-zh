# Java 中 `LocalDateTime.of()` 方法示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-ofint-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofint-method-in-java-with-examples/)

## 1. `of(int year, int month, int dayOfMonth, int hour, int minute)` 方法

`LocalDateTime` 类中的 `of(int year, int month, int dayOfMonth, int hour, int minute)` 方法用于根据输入的年、月、日、时、分创建 `LocalDateTime` 实例。该实例同时表示日期和时间。参数 `year`、`month` 和 `day` 用于确定日期，参数 `hour` 和 `minute` 用于确定时间。秒和纳秒将默认设置为零。

### 语法

```java
public static LocalDateTime of(int year,
                               int month,
                               int dayOfMonth,
                               int hour,
                               int minute)
```

### 参数
该方法接受 5 个参数：
*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – 整数型，代表一年中的月份。范围从 1 (一月) 到 12 (十二月)。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。

### 返回值
该方法返回根据输入值计算得出的 `LocalDateTime`。

### 异常
如果任何字段的值超出上述范围，或者月中的某一天对于该月-年无效，则该方法抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, int month, int dayOfMonth, int hour, int minute)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
// int dayOfMonth, int hour, int minute) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2020, 5, 13, 6, 30);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

### 输出

```java
DateTime: 2020-05-13T06:30
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
// int dayOfMonth, int hour, int minute) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2019, 5, 13, 6, 30);

        // print year only
        System.out.println(
            "Year: "
            + localdatetime.getYear());
    }
}
```

### 输出

```java
Year: 2019
```

## 2. `of(int year, int month, int dayOfMonth, int hour, int minute, int second)` 方法

`LocalDateTime` 类中的 `of(int year, int month, int dayOfMonth, int hour, int minute, int second)` 方法用于根据输入的年、月、日、时、分、秒创建 `LocalDateTime` 实例。参数 `year`、`month` 和 `day` 用于确定日期，参数 `hour`、`minute` 和 `second` 用于确定时间。此方法在不需要纳秒时使用，因为 `nanoSecond` 的值将默认设置为零。

### 语法

```java
public static LocalDateTime of(int year,
                               int month,
                               int dayOfMonth,
                               int hour,
                               int minute,
                               int second)
```

### 参数
该方法接受六个参数：
*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – 整数型，代表一年中的月份。范围从 1 (一月) 到 12 (十二月)。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。
*   `second` – 整数型，表示一分钟内的秒。范围从 0 到 59。

### 返回值
该方法返回根据输入值计算得出的 `LocalDateTime`。

### 异常
如果任何字段的值超出上述范围，或者月中的某一天对于该月-年无效，则该方法抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, int month, int dayOfMonth, int hour, int minute, int second)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
// int dayOfMonth, int hour, int minute,
// int second) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(
                2020, 5, 13, 6, 30, 45);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

### 输出

```java
DateTime: 2020-05-13T06:30:45
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
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
                2019, 5, 13, 6, 30, 45);

        // print dayofmonth only
        System.out.println(
            "DayOfMonth: "
            + localdatetime.getDayOfMonth());
    }
}
```

### 输出

```java
DayOfMonth: 13
```

## 3. `of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoSecond)` 方法

`LocalDateTime` 类中的 `of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoSecond)` 方法用于根据输入的年、月、日、时、分、秒和纳秒创建 `LocalDateTime` 实例。该实例同时表示日期和时间。参数 `year`、`month` 和 `day` 用于日期，参数 `hour`、`minute`、`second` 和 `nanosecond` 用于时间。

### 语法

```java
public static LocalDateTime of(int year,
                               int month,
                               int dayOfMonth,
                               int hour,
                               int minute,
                               int second,
                               int nanoOfSecond)
```

### 参数
该方法接受七个参数：
*   `year` – 整数型，代表年份。范围从最小年到最大年。
*   `month` – 整数型，代表一年中的月份。范围从 1 (一月) 到 12 (十二月)。
*   `dayOfMonth` – 整数类型，表示一个月中的某一天。范围从 1 到 31。
*   `hour` – 整数类型，代表一天中的小时。范围从 0 到 23。
*   `minute` – 整数类型，代表一小时中的分钟。范围从 0 到 59。
*   `second` – 整数型，表示一分钟内的秒。范围从 0 到 59。
*   `nanoOfSecond` – 整数型，代表纳秒。范围从 0 到 999,999,999。

### 返回值
该方法返回 `LocalDateTime`。

### 异常
如果任何字段的值超出范围，或者月日对于月年无效，此方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中的 `of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond)` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
// int dayOfMonth, int hour, int minute,
// int second, int nanoOfSecond) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.of(2020, 5, 13, 6,
                               30, 45, 20000);

        // print full date and time
        System.out.println("DateTime: "
                           + localdatetime);
    }
}
```

### 输出

```java
DateTime: 2020-05-13T06:30:45.000020
```

### 程序 2

```java
// Java program to demonstrate
// LocalDateTime.of(int year, int month,
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
                2019, 5, 13, 6,
                30, 45, 50000);

        // print nanoOfSecond only
        System.out.println(
            "NanoOfSecond: "
            + localdatetime.getNano());
    }
}
```

### 输出

```java
NanoOfSecond: 50000
```

**参考文献：**

1.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int))
2.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int, int))
3.  [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int, int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, int, int, int, int, int, int))