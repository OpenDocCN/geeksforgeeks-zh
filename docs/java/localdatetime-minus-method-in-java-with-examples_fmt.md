# Java 中的 LocalDateTime minus()方法，示例

> 原文:[https://www.geeksforgeeks.org/localdatetime-minus-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-minus-method-in-java-with-examples/)

在 `LocalDateTime` 类中，根据传递给它的参数，有两种类型的 `minus()` 方法。

### minus(long amountToSubtract, TemporalUnit unit)

`minus()` 是 `LocalDateTime` 类的一个方法，用于返回这个 `LocalDateTime` 的一个副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public LocalDateTime minus(long amountToSubtract,
                           TemporalUnit unit)
```

**参数:** 该方法接受两个参数：`amountToSubtract` 可以为负数，以及 `unit` 为要减去的量的单位，不为空。

**返回值:** 该方法基于该 `LocalDateTime` 返回一个新的 `LocalDateTime`，减去指定的金额。

**异常:** 该方法抛出以下异常:

*   `DateTimeException` – 如果无法进行减法运算
*   `UnsupportedTemporalTypeException` – 如果不支持该单位
*   `ArithmeticException` – 如果出现数值溢出

下面的程序说明了 `minus()` 方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // subtract 200 DAYS to LocalDateTime
        LocalDateTime value
            = ldt.minus(200, ChronoUnit.DAYS);

        // print result
        System.out.println("LocalDateTime after subtracting DAYS: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after subtracting DAYS: 2019-06-14T19:15:30
```

### minus(TemporalAmount amountToSubtract)

`minus()` 方法是 `LocalDateTime` 类的一个方法，用来返回这个 `LocalDateTime` 的一个副本，减去指定的数量。该金额通常为 `Period` 或 `Duration`，但也可以是实现 `TemporalAmount` 接口的任何其他类型。

**语法:**

```java
public LocalDateTime minus(TemporalAmount amountToSubtract)
```

**参数:** 此方法接受一个单参数 `amountToSubtract` 为要减去的量，不应为空。

**返回值:** 该方法基于该日期时间进行减法运算，返回一个新的 `LocalDateTime`，不为空。

**异常:**
此方法抛出以下异常:

*   `DateTimeException` – 如果无法进行减法运算
*   `ArithmeticException` – 如果出现数值溢出

下面的程序说明了 `minus()` 方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDateTime.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + ldt.toString());

        // subtract 10 Days to LocalDateTime
        LocalDateTime value
            = ldt.minus(Period.ofDays(10));

        // print result
        System.out.println("LocalDateTime after subtracting Days: "
                           + value);
    }
}
```

**Output:**

```java
Original LocalDateTime: 2019-12-31T19:15:30
LocalDateTime after subtracting Days: 2019-12-21T19:15:30
```

**参考文献:**
[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(java.time.temporal.TemporalAmount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(java.time.temporal.TemporalAmount))
[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(long, java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#minus(long, java.time.temporal.TemporalUnit))