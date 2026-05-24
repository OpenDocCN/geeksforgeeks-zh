# Java 中的 LocalDate minus() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/localdate-minus-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-minus-method-in-java-with-examples/)

在 `LocalDate` 类中，根据传递给它的参数，有两种类型的 `minus()` 方法。

## minus(long amountToSubtract, TemporalUnit unit)

`LocalDate` 类中的 `minus()` 方法用于返回此 `LocalDate` 的一个副本，其中指定数量的单位被减去。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

### 语法

```java
public LocalDate minus(long amountToSubtract,
                       TemporalUnit unit)
```

### 参数

该方法接受两个参数：

*   `amountToSubtract`：要从结果中减去的单位的数量，可以是负数。
*   `unit`：要减去的量的单位。

### 返回值

该方法根据此日期时间减去指定的金额，返回一个 `LocalDate`。

### 异常

该方法抛出以下异常：

*   `DateTimeException`：如果不能做减法。
*   `UnsupportedTemporalTypeException`：如果不支持该单位。
*   `ArithmeticException`：如果出现数值溢出。

下面的程序说明了 `minus()` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDate.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 12 Years to LocalDate
        LocalDate value
            = zonedlt.minus(12, ChronoUnit.YEARS);

        // print result
        System.out.println("LocalDate after "
                           + "subtracting Months: "
                           + value);
    }
}
```

### 输出

```java
LocalDate after subtracting Months: 2006-12-06
```

## minus(TemporalAmount amountToSubtract)

`LocalDate` 类中的 `minus()` 方法用于返回此 `LocalDate` 的一个副本，其中指定的数量被减去。该金额通常为 `Period` 或 `Duration`，但也可以是实现 `TemporalAmount` 接口的任何其他类型。

### 语法

```java
public LocalDate minus(TemporalAmount amountToSubtract)
```

### 参数

此方法接受一个单一参数 `amountToSubtract`，为要减去的量，不应为 `null`。

### 返回值

该方法基于此日期时间进行减法运算，返回一个 `LocalDate`，不为 `null`。

### 异常

该方法抛出以下异常：

*   `DateTimeException`：如果不能做减法。
*   `ArithmeticException`：如果出现数值溢出。

下面的程序说明了 `minus()` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalDate.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 30 Days to LocalDate
        LocalDate value
            = zonedlt.minus(Period.ofDays(30));

        // print result
        System.out.println("LocalDate after"
                           + " subtracting Days: "
                           + value);
    }
}
```

### 输出

```java
LocalDate after subtracting Days: 2018-11-06
```

## 参考

*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(java.time.temporal.TemporalAmount)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(java.time.temporal.TemporalAmount))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(long, java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minus(long, java.time.temporal.TemporalUnit))