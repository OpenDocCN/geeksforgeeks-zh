# Java 中的 LocalTime.until() 方法示例

> 原文：[https://www.geeksforgeeks.org/localtime-until-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-until-method-in-java-with-examples/)

`LocalTime` 类的 `until()` 方法用于计算两个 `LocalTime` 对象之间的时间量，使用的是 `TemporalUnit`。起点是此实例，终点是作为参数传递的指定 `LocalTime`。如果结束时间在开始时间之前，结果将为负数。计算返回一个整数，表示两个 `LocalTime` 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

## 语法

```java
public long until(Temporal endExclusive, TemporalUnit unit)
```

## 参数

该方法接受两个参数：
*   `endExclusive`：结束时间（不含），转换为 `LocalTime`。
*   `unit`：计量时间量的单位。

## 返回值

此方法返回此 `LocalTime` 和结束 `LocalTime` 之间的时间量。

## 异常

该方法抛出以下异常：
*   `DateTimeException` – 如果无法计算时间量，或者结束时间无法转换为 `LocalTime`。
*   `UnsupportedTemporalTypeException` – 如果单位不受支持。
*   `ArithmeticException` – 如果出现数字溢出。

以下程序说明了 `until()` 方法：

## 程序 1

```java
// Java program to demonstrate
// LocalTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("19:21:12");

        LocalTime l2
            = LocalTime
                  .parse("23:12:31.123");

        // apply until method of LocalTime class
        long result
            = l2.until(l1,
                       ChronoUnit.SECONDS);

        // print results
        System.out.println("Result in SECONDS: "
                           + result);
    }
}
```

**输出：**

```java
Result in SECONDS: -13879
```

## 程序 2

```java
// Java program to demonstrate
// LocalTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalTime objects
        LocalTime l1
            = LocalTime
                  .parse("19:21:12");

        LocalTime l2
            = LocalTime
                  .parse("23:12:31.123");

        // apply until method of LocalTime class
        long result
            = l1.until(l2,
                       ChronoUnit.HOURS);

        // print results
        System.out.println("Result in HOURS: "
                           + result);
    }
}
```

**输出：**

```java
Result in HOURS: 3
```

## 参考文献

[`https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit)`](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))