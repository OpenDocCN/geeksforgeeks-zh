# Java 中的 LocalDate.until() 方法示例

> 原文：[https://www.geeksforgeeks.org/localdate-untiltemporaltemporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-untiltemporaltemporalunit-method-in-java-with-examples/)

`until()` 方法属于 `LocalDate` 类，用于计算两个 `LocalDate` 对象之间的时间量，使用的是 `TemporalUnit`。起点是此实例，终点是作为参数传递的指定 `LocalDate`。如果终点在起点之前，结果将为负数。计算返回一个整数，代表两个 `LocalDate` 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

## 语法

```java
public long until(Temporal endExclusive, TemporalUnit unit)
```

## 参数

该方法接受两个参数：
- `endExclusive`：结束日期，将被转换为 `LocalDate`。
- `unit`：用于计量时间量的单位。

## 返回值

此方法返回此 `LocalDate` 和结束 `LocalDate` 之间的时间量。

## 异常

该方法抛出以下异常：
- `DateTimeException` – 如果无法计算时间量，或者结束时态无法转换为 `LocalDate`。
- `UnsupportedTemporalTypeException` – 如果单位不被支持。
- `ArithmeticException` – 如果出现数字溢出。

## 程序 1

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until the method of LocalDate class
        long result
            = l2.until(l1,
                       ChronoUnit.DAYS);

        // print results
        System.out.println("Result in DAYS: "
                           + result);
    }
}
```

**输出：**

```java
Result in DAYS: 42
```

## 程序 2

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until()
        long result
            = l2.until(l1,
                       ChronoUnit.MONTHS);

        // print results
        System.out.println("Result in MONTHS: "
                           + result);
    }
}
```

**输出：**

```java
Result in MONTHS: 1
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))