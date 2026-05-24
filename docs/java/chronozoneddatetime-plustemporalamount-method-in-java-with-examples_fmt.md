# ChronoZonedDateTime.plus(TemporalAmount)方法详解

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-plustemporalamount-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-plustemporalamount-method-in-java-with-examples/)

`plus()`方法是`ChronoZonedDateTime`类的一个方法，用于返回这个日期时间的一个副本，并将指定的数量加到日期时间上。该金额通常为`Period`或`Duration`，但也可以是实现`TemporalAmount`接口的任何其他类型。

## 语法

```java
public ChronoZonedDateTime plus(TemporalAmount amountToAdd)
```

## 参数

此方法只接受一个参数`amountToAdd`，即要加的金额，不应该为`null`。

## 返回值

该方法基于该日期时间返回`ChronoZonedDateTime`，并进行加法运算，不为`null`。

## 异常

该方法抛出以下异常：

*   `DateTimeException`：如果无法添加
*   `ArithmeticException`：如果出现数值溢出

下面的程序说明了`plus()`方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoZonedDateTime.plus() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // add 10 Days to ChronoZonedDateTime
        ChronoZonedDateTime value
            = zonedlt.plus(Period.ofDays(10));

        // print result
        System.out.println("ChronoZonedDateTime after"
                           + " adding Days:\n "
                           + value);
    }
}
```

**Output:**

```java
ChronoZonedDateTime after adding Days:
 2018-12-16T19:21:12.123+05:30[Asia/Calcutta]
```

**参考：**[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#plus-java.time.temporal.TemporalAmount-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#plus-java.time.temporal.TemporalAmount-)