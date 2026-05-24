# Java 中的 Duration plus(long, TemporalUnit) 方法

> 原文: [https://www.geeksforgeeks.org/duration-pluslong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-pluslong-temporalunit-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `plus(long, TemporalUnit)` 方法用于获取该持续时间的不可变副本，并添加指定的持续时间，作为参数传递。要添加的持续时间是通过将作为参数传递的单位中的数量转换为数量来决定的。

**语法:**

```java
public Duration plus(long amountToAdd, TemporalUnit unit)
```

**参数:** 此方法接受两个参数:

*   `amountToAdd`：要添加的量，可以是正数或负数，但不能为空。
*   `unit`：要添加的时间单位，不能为空。

**返回值:** 该方法返回一个 `Duration`，它是一个现有持续时间的不可变副本，并添加了持续时间的参数量。

**异常:** 此方法抛出:

*   `ArithmeticException`：如果发生数值溢出。
*   `UnsupportedTemporalTypeException`：如果不支持该单位。

以下示例说明了 `Duration.plus()` 方法:

## 示例 1

```java
// Java code to illustrate plus() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plus() method
        System.out.println(
            duration1
                .plus(5, ChronoUnit.HOURS));
    }
}
```

**输出:**

```java
PT56H4M
```

## 示例 2

```java
// Java code to illustrate plus() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plus() method
        System.out.println(
            duration1
                .plus(2, ChronoUnit.DAYS));
    }
}
```

**输出:**

```java
PT48H4M
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plus-long-java.time.temporal.TemporalUnit-)