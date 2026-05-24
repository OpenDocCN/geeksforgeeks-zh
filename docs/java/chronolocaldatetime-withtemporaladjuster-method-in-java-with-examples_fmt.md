# Java 中带(TemporalAdjuster)方法的 ChronoLocalDateTime，示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-withtemporaladjuster-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-withtemporaladjuster-method-in-java-with-examples/)

使用`ChronoLocalDateTime`接口的`with(TemporalAdjuster)`方法，使用时间调整调节器调整该日期时间，调整后返回调整后的日期时间的副本。使用指定的调整器策略对象进行调整。`ChronoLocalDateTime`的这个实例是不可变的，不受此方法调用的影响。简单的调整器用于设置其中一个字段，例如年份字段，在该字段中，更复杂的调整器可能会将时间设置为一年中的最后一天。

## 语法

```java
default ChronoLocalDateTime with(TemporalAdjuster adjuster)
```

## 参数

该方法接受`adjuster`作为参数，调节器使用该参数。

## 返回值

该方法基于此返回一个进行了调整的`ChronoLocalDateTime`。

## 异常

此方法抛出以下异常：

*   `DateTimeException` - 如果无法进行调整。
*   `ArithmeticException` - 如果发生数值溢出。

下面的程序说明了`with()`方法：

## 程序 1

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

// print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

// apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(Month.OCTOBER)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

// print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

### 输出

```java
ChronoLocalDateTime before adjustment: 2019-12-31T19:15:30
ChronoLocalDateTime after adjustment: 2019-10-01T19:15:30
```

## 程序 2

```java
// Java program to demonstrate
// ChronoLocalDateTime.with() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

// create ChronoLocalDateTime object
        ChronoLocalDateTime time
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

// print instance
        System.out.println("ChronoLocalDateTime before"
                           + " adjustment: "
                           + time);

// apply with method of ChronoLocalDateTime
        ChronoLocalDateTime updatedlocal
            = time.with(Month.JANUARY)
                  .with(TemporalAdjusters
                            .firstDayOfMonth());

// print instance
        System.out.println("ChronoLocalDateTime after"
                           + " adjustment: "
                           + updatedlocal);
    }
}
```

### 输出

```java
ChronoLocalDateTime before adjustment: 2018-10-25T23:12:31.123
ChronoLocalDateTime after adjustment: 2018-01-01T23:12:31.123
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#with-java.time.temporal.TemporalAdjuster-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#with-java.time.temporal.TemporalAdjuster-)