# Java 中的 `ChronoLocalDateTime.plus(TemporalAmount)` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-plustemporalamount-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-plustemporalamount-method-in-java-with-examples/)

`ChronoLocalDateTime` 接口的 `plus()` 方法用于返回该日期时间的副本，并将指定的数量添加到日期时间中。该金额通常为“期间”（`Period`）或“持续时间”（`Duration`），但也可以是实现 `TemporalAmount` 接口的任何其他类型。

## 语法

```java
default ChronoLocalDateTime plus(TemporalAmount amountToAdd)
```

## 参数
此方法只接受一个参数 `amountToAdd`，即要加的金额，不应该为 `null`。

## 返回值
此方法基于此日期时间返回一个新的 `ChronoLocalDateTime` 对象，并进行加法运算，不为 `null`。

## 异常
该方法抛出以下异常：
*   `DateTimeException` – 如果无法添加
*   `ArithmeticException` – 如果出现数值溢出

下面的程序说明了 `plus()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.plus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ChronoLocalDateTime instance
        ChronoLocalDateTime ldt
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // Get the String representation of this ChronoLocalDateTime
        System.out.println("Original ChronoLocalDateTime: "
                           + ldt.toString());

        // add 10 Days to ChronoLocalDateTime
        ChronoLocalDateTime value
            = ldt.plus(Period.ofDays(10));

        // print result
        System.out.println("ChronoLocalDateTime after adding Days: "
                           + value);
    }
}
```

**输出：**

```java
Original ChronoLocalDateTime: 2019-12-31T19:15:30
ChronoLocalDateTime after adding Days: 2020-01-10T19:15:30
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#plus-java.time.temporal.TemporalAmount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#plus-java.time.temporal.TemporalAmount-)