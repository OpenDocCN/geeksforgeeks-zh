# Java中的ChronoLocalDateTime.toEpochSecond()方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-toepochsecond-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-toepochsecond-method-in-java-with-examples/)

`ChronoLocalDateTime`类的`toEpochSecond()`方法用于将该计时本地日期时间转换为自1970-01-01T00:00:00Z以来的秒数。该方法将此`ChronoLocalDateTime`与作为参数传递的偏移量相结合，以计算历元秒值，即从1970-01-01T00:00:00Z经过的秒数。纪元后时间线上的瞬间是正的，更早的是负的。

## 语法
```java
default long toEpochSecond(ZoneOffset offset)
```

## 参数
该方法接受一个参数`offset`，即区域偏移量。

## 返回值
此方法返回`long`，为1970-01-01T00:00:00Z纪元以来的秒数，可能为负数。

以下程序说明了`toEpochSecond()`方法：

## 程序1
```java
// Java program to demonstrate
// ChronoLocalDateTime.toEpochSecond() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

// print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

// create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

// print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

// print result
        System.out.println("Epoch Second: "
                           + time.toEpochSecond(zone));
    }
}
```

## 输出
```java
ChronoLocalDateTime: 2019-12-31T19:15:30
Passed ZoneOffset: Z
Epoch Second: 1577819730
```

## 程序2
```java
// Java program to demonstrate
// ChronoLocalDateTime.toEpochSecond() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime.parse(
                "2018-10-25T23:12:31.123");

// print ChronoLocalDateTime
        System.out.println("ChronoLocalDateTime: "
                           + time);

// create ZoneId
        ZoneOffset zone = ZoneOffset.of("Z");

// print ZoneId
        System.out.println("Passed ZoneOffset: "
                           + zone);

// print result
        System.out.println("Epoch Second: "
                           + time.toEpochSecond(zone));
    }
}
```

## 输出
```java
ChronoLocalDateTime: 2018-10-25T23:12:31.123
Passed ZoneOffset: Z
Epoch Second: 1540509151
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#toEpochSecond-java.time.ZoneOffset-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#toEpochSecond-java.time.ZoneOffset-)