# Java 中的 `ChronoLocalDate minus(long, TemporalUnit)` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-minuslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-minuslong-temporalunit-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `minus(long, TemporalUnit)` 方法，用于返回该计时日期的一个副本，其中指定数量的单位减去计时日期。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

## 语法

```java
public ChronoLocalDate minus(long amountToSubtract,
                       TemporalUnit unit)
```

## 参数

此方法接受两个参数：

*   `amountToSubtract`：要减去的单位数量，可以是负数。
*   `unit`：要减去的单位。

## 返回值

该方法根据该日期时间减去指定的金额返回 `ChronoLocalDate`。

## 异常

此方法抛出以下异常：

*   `DateTimeException`：如果减法无法执行。
*   `UnsupportedTemporalTypeException`：如果单位不被支持。
*   `ArithmeticException`：如果发生数值溢出。

下面的程序说明了 `minus()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoLocalDate.minus() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 12 Years to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.minus(12, ChronoUnit.YEARS);

        // print result
        System.out.println("ChronoLocalDate after "
                           + "subtracting Months: "
                           + value);
    }
}
```

## 输出

```java
ChronoLocalDate after subtracting Months: 2006-12-06
```

## 参考文献

T2