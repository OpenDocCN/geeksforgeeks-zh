# Java 中的 Instant minus() 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-minus-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-minus-method-in-java-with-examples/)

在 `Instant` 类中，根据传递给它的参数，有两种类型的 `minus()` 方法。

## minus(long amountToSubtract, TemporalUnit unit)

`Instant` 类的 `minus()` 方法用于返回此瞬间的一个副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法：**

```java
public Instant minus(long amountToSubtract,
                     TemporalUnit unit)
```

**参数：** 该方法接受两个参数：
*   `amountToSubtract` 是要从结果中减去的单位的数量，可以是负数。
*   `unit` 是要减去的金额的单位，不为空。

**返回值：** 该方法基于此瞬间返回 `Instant`，减去指定的金额。

**异常：** 该方法抛出以下异常：
*   `DateTimeException` – 如果无法进行减法运算。
*   `UnsupportedTemporalTypeException` – 如果不支持该单位。
*   `ArithmeticException` – 如果出现数值溢出。

下面的程序说明了 `minus()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// Instant.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {
        // create an Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // subtract 20 DAYS to Instant
        Instant value
            = instant.minus(20, ChronoUnit.DAYS);

        // print result
        System.out.println("Instant after subtracting DAYS: "
                           + value);
    }
}
```

**输出：**

```java
Instant after subtracting DAYS: 2018-12-10T19:34:50.630Z
```

## minus(TemporalAmount amountToSubtract)

`Instant` 类的 `minus()` 方法用于返回此瞬间的副本，并减去指定数量的日期时间。该金额通常为 `Period` 或 `Duration`，但也可以是实现 `TemporalAmount` 接口的任何其他类型。

**语法：**

```java
public Instant minus(TemporalAmount amountToSubtract)
```

**参数：** 此方法接受一个单参数 `amountToSubtract`，为要减去的量，不应为空。

**返回值：** 该方法基于此日期时间进行减法运算，返回 `Instant`，不为空。

**异常：** 该方法抛出以下异常：
*   `DateTimeException` – 如果无法进行减法运算。
*   `ArithmeticException` – 如果出现数值溢出。

下面的程序说明了 `minus()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// Instant.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {
        // create an Instant object
        Instant inst
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // subtract 10 Days to Instant
        Instant value
            = inst.minus(Period.ofDays(10));

        // print result
        System.out.println("Instant after subtracting Days: "
                           + value);
    }
}
```

**输出：**

```java
Instant after subtracting Days: 2018-12-20T19:34:50.630Z
```

**参考文献：**
*   [https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(java.time.temporal.TemporalAmount)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(java.time.temporal.TemporalAmount))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(long, java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minus(long, java.time.temporal.TemporalUnit))