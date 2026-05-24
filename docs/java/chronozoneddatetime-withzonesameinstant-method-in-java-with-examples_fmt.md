# ChronoZonedDateTime.withZoneSameInstant() 方法详解

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-withzonesameinstant-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withzonesameinstant-method-in-java-with-examples/)

`ChronoZonedDateTime` 接口的 `withZoneSameInstant()` 方法，用于通过更改时区并保持相同的瞬时点，返回该日期时间对象的副本。这种方法基于保持相同的瞬间，因此局部时间线上的间隙和重叠对结果没有影响。

## 语法

```java
ChronoZonedDateTime withZoneSameInstant(ZoneId zone)
```

## 参数

此方法接受一个单参数 `zone`，即时区更改为。它不应为 `null`。

## 返回值

该方法根据请求区域的日期时间返回一个 `ChronoZonedDateTime`。

## 异常

此方法抛出 `DateTimeException`：如果结果超出支持的日期范围。

下面的程序说明了 `withZoneSameInstant()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

// print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

// apply withZoneSameInstant()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameInstant(
                      ZoneId.of("Pacific/Fiji"));

// print ChronoZonedDateTime after withZoneSameInstant()
        System.out.println("ChronoZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

### 输出

```java
ChronoZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime of Fuji: 2018-12-07T02:51:12.123+13:00[Pacific/Fiji]
```

### 程序 2

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameInstant() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

// print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime of Calcutta: "
                           + zonedDT);

// apply withZoneSameInstant()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameInstant(
                      ZoneId.of("Canada/Yukon"));

// print ChronoZonedDateTime after withZoneSameInstant()
        System.out.println("ChronoZonedDateTime of yukon: "
                           + zonedDT2);
    }
}
```

### 输出

```java
ChronoZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ChronoZonedDateTime of yukon: 2018-10-25T14:12:31.123-07:00[Canada/Yukon]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameInstant-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameInstant-java.time.ZoneId-)