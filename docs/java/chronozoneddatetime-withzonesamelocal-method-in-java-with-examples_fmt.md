# Java 中的 `withZoneSameLocal()` 方法

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-withzonesamelocal-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-withzonesamelocal-method-in-java-with-examples/)

`ChronoZonedDateTime` 接口的 `withZoneSameLocal()` 方法，用于通过更改时区返回该日期时间对象的副本，而不改变其表示的瞬间。这种方法基于保持相同的瞬间，因此局部时间线上的间隙和重叠对结果没有影响。

## 语法

```java
ChronoZonedDateTime withZoneSameLocal(ZoneId zone)
```

## 参数

此方法接受一个单参数 `zone`，即要更改为的时区。它不应为 `null`。

## 返回值

该方法根据请求的时区返回一个 `ChronoZonedDateTime` 对象。

## 示例

下面的程序说明了 `withZoneSameLocal()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameLocal() method

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

        // apply withZoneSameLocal()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameLocal(
                      ZoneId.of("Pacific/Fiji"));

        // print ChronoZonedDateTime after withZoneSameLocal()
        System.out.println("ChronoZonedDateTime of Fuji: "
                           + zonedDT2);
    }
}
```

**输出：**

```java
ChronoZonedDateTime of Calcutta: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ChronoZonedDateTime of Fuji: 2018-12-06T19:21:12.123+13:00[Pacific/Fiji]
```

### 程序 2

```java
// Java program to demonstrate
// ChronoZonedDateTime.withZoneSameLocal() method

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

        // apply withZoneSameLocal()
        ChronoZonedDateTime zonedDT2
            = zonedDT
                  .withZoneSameLocal(
                      ZoneId.of("Canada/Yukon"));

        // print ChronoZonedDateTime after withZoneSameLocal()
        System.out.println("ChronoZonedDateTime of yukon: "
                           + zonedDT2);
    }
}
```

**输出：**

```java
ChronoZonedDateTime of Calcutta: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
ChronoZonedDateTime of yukon: 2018-10-25T23:12:31.123-07:00[Canada/Yukon]
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameLocal-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#withZoneSameLocal-java.time.ZoneId-)