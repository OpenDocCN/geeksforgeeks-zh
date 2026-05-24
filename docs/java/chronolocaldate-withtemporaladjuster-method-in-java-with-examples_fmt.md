# Java 中 ChronoLocalDate.with() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-withtemporaladjuster-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-withtemporaladjuster-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `with()` 方法，使用作为参数传递的时间调整值调整该日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。`ChronoLocalDate` 的这个实例是不可变的，不受这个方法调用的影响。

## 语法

```java
public ChronoLocalDate with(TemporalAdjuster adjuster)
```

## 参数

该方法接受 `adjuster` 作为参数，调节器使用该参数。

## 返回值

该方法基于此返回一个进行了调整的 `ChronoLocalDate`。

## 异常

此方法抛出以下异常：

*   `DateTimeException` - 如果无法进行调整。
*   `ArithmeticException` - 如果发生数值溢出。

下面的程序说明了 `with()` 方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoLocalDate.with() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        ChronoLocalDate local
            = LocalDate.parse(
                "2018-12-06");

        // print instance
        System.out.println("ChronoLocalDate before"
                           + " adjustment: "
                           + local);

        // apply with method of LocalDate class
        ChronoLocalDate updatedlocal
            = local.with(Month.MARCH)
                  .with(TemporalAdjusters
                            .lastDayOfMonth());

        // print instance
        System.out.println("ChronoLocalDate after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

## 输出

```java
ChronoLocalDate before adjustment: 2018-12-06
ChronoLocalDate after adjustment: 2018-03-31
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#with-java.time.temporal.TemporalAdjuster-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#with-java.time.temporal.TemporalAdjuster-)