# Java 中 LocalDateTime 类的 with() 方法示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-with-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-with-method-in-java-with-examples/)

在 `LocalDateTime` 类中，根据传递给它的参数，有两种类型的 `with()` 方法。

## 带 `TemporalAdjuster` 参数

使用 `LocalDateTime` 类的 `with(TemporalAdjuster adjuster)` 方法，可以使用一个 `TemporalAdjuster` 来调整该日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。`LocalDateTime` 的这个实例是不可变的，不受此方法调用的影响。简单的调整器用于设置其中一个字段，例如年份字段，而更复杂的调整器可能会将时间设置为一年中的最后一天。

**语法：**

```java
public LocalDateTime with(TemporalAdjuster adjuster)
```

**参数：** 该方法接受 `adjuster` 作为参数，调整器使用该参数。

**返回值：** 该方法根据调整后的值返回一个 `LocalDateTime`。

**异常：** 该方法抛出以下异常：
*   `DateTimeException` – 如果无法进行调整。
*   `ArithmeticException` – 如果出现数值溢出。

下面的程序说明了 `with()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime object
        LocalDateTime local
            = LocalDateTime.parse(
                "2020-12-31T10:15:30");

        // print instance
        System.out.println("LocalDateTime before"
                           + " adjustment: "
                           + local);

        // apply with method of LocalDateTime class
        LocalDateTime updatedlocal
            = local.with(Month.OCTOBER)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

        // print instance
        System.out.println("LocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

**Output：**

```java
LocalDateTime before adjustment: 2020-12-31T10:15:30
LocalDateTime after adjustment: 2020-10-01T10:15:30
```

## 带 `TemporalField` 和 `long` 参数

使用 `LocalDateTime` 类的 `with(TemporalField field, long newValue)` 方法，用于将 `LocalDateTime` 的指定字段设置为新值，并返回新时间的副本。此方法可用于更改任何支持的字段，如年、日、月、小时、分钟或秒。如果由于字段不受支持或其他原因而无法设置新值，则会引发异常。`LocalDateTime` 的这个实例是不可变的，不受此方法调用的影响。

**语法：**

```java
public LocalDateTime with(TemporalField field, long newValue)
```

**参数：** 此方法接受 `field` 和 `newValue` 作为参数，前者是要在结果中设置的字段，后者是结果中字段的新值。

**返回值：** 该方法基于此返回一个带有指定字段集的 `LocalDateTime`。

**异常：** 该方法抛出以下异常：
*   `DateTimeException` – 如果无法进行调整。
*   `UnsupportedTemporalTypeException` – 如果不支持该字段。
*   `ArithmeticException` – 如果出现数值溢出。

下面的程序说明了 `with()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDateTime.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime object
        LocalDateTime local
            = LocalDateTime.parse(
                "2021-01-01T19:55:30");

        // print instance
        System.out.println("LocalDateTime before"
                           + " applying method: "
                           + local);

        // apply with method of LocalDateTime class
        LocalDateTime updatedlocal
            = local.with(ChronoField.YEAR, 2017);

        // print instance
        System.out.println("LocalDateTime after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output：**

```java
LocalDateTime before applying method: 2021-01-01T19:55:30
LocalDateTime after applying method: 2017-01-01T19:55:30
```

**参考文献：**
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#with(java.time.temporal.TemporalAdjuster)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#with(java.time.temporal.TemporalAdjuster))
*   [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#with(java.time.temporal.TemporalField, long)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#with(java.time.temporal.TemporalField, long))