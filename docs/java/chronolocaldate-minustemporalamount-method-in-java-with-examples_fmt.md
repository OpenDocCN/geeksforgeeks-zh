# Java 中的 ChronoLocalDate.minus(TemporalAmount) 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-minustemporalamount-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-minustemporalamount-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `minus(TemporalAmount)` 方法，用于返回该 `ChronoLocalDate` 的副本，其中减去指定的金额。该金额通常为“期间”（`Period`）或“持续时间”（`Duration`），但也可以是实现 `TemporalAmount` 接口的任何其他类型。

## 语法

```java
public ChronoLocalDate minus(TemporalAmount amountToSubtract)
```

## 参数

此方法接受一个单参数 `amountToSubtract`，为要减去的量，不应为 `null`。

## 返回值

该方法基于该日期时间进行减法运算，返回 `ChronoLocalDate`，不为 `null`。

## 异常

此方法抛出以下异常：

*   **日期时间异常**：如果减法无法进行。
*   **算术异常**：如果发生数值溢出。

下面的程序说明了 `minus()` 方法：

## 示例 1

```java
// Java program to demonstrate
// ChronoLocalDate.minus() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate zonedlt
            = LocalDate.parse("2018-12-06");

        // subtract 30 Days to ChronoLocalDate
        ChronoLocalDate value
            = zonedlt.minus(Period.ofDays(30));

        // print result
        System.out.println("ChronoLocalDate after"
                           + " subtracting Days: "
                           + value);
    }
}
```

## 输出

```java
ChronoLocalDate after subtracting Days: 2018-11-06
```

## 参考文献

T2