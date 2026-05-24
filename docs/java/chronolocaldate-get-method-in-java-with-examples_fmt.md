# Java 中的 ChronoLocalDate get()方法，示例

> 原文：[`https://www.geeksforgeeks.org/chronolocaldate-get-method-in-java-with-examples/`](https://www.geeksforgeeks.org/chronolocaldate-get-method-in-java-with-examples/)

Java 中的 `ChronoLocalDate` 接口的 `get()` 方法从该日期获取指定字段的值作为 `int`。

## 语法

```java
public int get(TemporalField field)
```

## 参数

该方法接受一个参数 `field`，该字段是要获取的字段，不允许为 `null`。

## 返回值

返回该字段的值。

## 异常

该方法抛出以下三个异常：

*   `DateTimeException`：如果无法获取字段的值或者该值超出了字段的有效值范围，则会引发此异常。
*   `UnsupportedTemporalTypeException`：如果字段不受支持或者值的范围超过一个整数，将引发此异常。
*   `ArithmeticException`：如果出现数值溢出，则抛出该异常。

## 程序 1

下面的程序举例说明了 Java 中的 `get()` 方法。

```java
// Program to illustrate the get() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDate dt
            = LocalDate.parse("2017-02-16");
        System.out.println(dt.get(
            ChronoField.MONTH_OF_YEAR));
    }
}
```

**Output:**

```java

```

## 程序 2

```java
// Program to illustrate the get() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        try {
            ChronoLocalDate dt
                = LocalDate.parse("2017-02-30");
            System.out.println(dt.get(
                ChronoField.MONTH_OF_YEAR));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.time.format.DateTimeParseException:
 Text '2017-02-30' could not be parsed:
 Invalid date 'FEBRUARY 30'
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#get-java.time.temporal.TemporalField-`](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#get-java.time.temporal.TemporalField-)