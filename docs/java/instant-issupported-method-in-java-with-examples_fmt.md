# Java 中的 `isSupported()` 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-issupported-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-issupported-method-in-java-with-examples/)

在 `Instant` 类中，根据传递给它的参数，有两种类型的 `isSupported()` 方法。

## `isSupported(TemporalField)` 方法

`isSupported()` 是 `Instant` 类的一个方法，用来检查指定的字段是否被 `Instant` 类支持。也就是说，使用这个方法我们可以检查这个 `Instant` 是否可以查询到指定的字段。

计时场支持的字段有：

*   `NANO_OF_SECOND`
*   `MICRO_OF_SECOND`
*   `MILLI_OF_SECOND`
*   `INSTANT_SECONDS`

所有其他时间域实例都将返回 `false`。

**语法：**

```java
public boolean isSupported(TemporalField field)
```

**参数：** 此方法接受一个单参数 `field`，即要检查的字段。
**返回值：** 此方法返回 `boolean` 值。如果该字段在此时刻受支持，则返回 `true`，否则返回 `false`。

下面的程序说明了 `isSupported()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// Instant.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // check Milli of Second value from instant
        boolean value
            = instant.isSupported(
                ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field is supported: "
                           + value);
    }
}
```

**输出**

```java
MilliSecond Field is supported: true
```

## `isSupported(TemporalUnit)` 方法

`isSupported()` 是 `Instant` 类的一个方法，用来检查 `Instant` 类是否支持指定的单位。这意味着使用这个方法我们可以检查这个 `Instant` 是否可以查询到指定的单位。

计时单位支持的字段有：

*   `NANOS`
*   `MICROS`
*   `MILLIS`
*   `SECONDS`
*   `MINUTES`
*   `HOURS`
*   `HALF_DAYS`
*   `DAYS`

所有其他计时单位实例将返回 `false`。

**语法：**

```java
public boolean isSupported(TemporalUnit unit)
```

**参数：** 该方法只接受一个参数 `unit`，即要检查的单位。
**返回值：** 如果该字段在该时刻被支持，则该方法返回 `boolean` 值 `true`，否则返回 `false`。

下面的程序说明了 `isSupported()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// Instant.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // check MILLIS ChronoUnit supported in instant
        boolean value
            = instant.isSupported(ChronoUnit.MILLIS);

        // print result
        System.out.println("ChronoUnit MILLIS is  supported: "
                           + value);
    }
}
```

**输出：**

```java
ChronoUnit MILLIS is  supported: true
```

**参考：**
[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalField))
[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#isSupported(java.time.temporal.TemporalUnit))