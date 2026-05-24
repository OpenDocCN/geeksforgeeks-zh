# Java 中的 ChronoZonedDateTime.toLocalDateTime() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-tolocaldatetime-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-tolocaldatetime-method-in-java-with-examples/)

一个 `ChronoZonedDateTime` 接口的 `toLocalDateTime()` 方法用于将该时区日期时间转换为本地日期时间。

## 语法

```java
default LocalDateTime toLocalDateTime()
```

## 参数

该方法不接受任何参数。

## 返回值

此方法返回 `LocalDateTime`，它与此 `ChronoZonedDateTime` 表示的 `LocalDateTime` 相同。

下面的程序说明了 `toLocalDateTime()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.toLocalDateTime() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

// print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

// print result
        System.out.println("LocalDateTime: "
                           + time.toLocalDateTime());
    }
}
```

## 输出

```java
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalDateTime: 2018-12-06T19:21:12.123
```

## 程序 2

```java
// Java program to demonstrate
// ChronoZonedDateTime.toLocalDateTime() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

// print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

// print result
        System.out.println("LocalDateTime: "
                           + time.toLocalDateTime());
    }
}
```

## 输出

```java
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
LocalDateTime: 1918-10-25T23:12:38.543
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toLocalDateTime--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toLocalDateTime--)