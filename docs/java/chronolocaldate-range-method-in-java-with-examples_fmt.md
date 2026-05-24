# Java 中的 ChronoLocalDate range()方法，示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-range-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-range-method-in-java-with-examples/)

`ChronoLocalDate` 接口的 `range()` 方法用于获取作为参数传递的字段的有效值范围。此方法返回一个 `ValueRange` 对象，该对象包含字段的最小和最大有效值。当字段不受支持时，将引发异常。这个 `ChronoLocalDate` 有助于提高返回范围的准确性。

## 语法

```java
public ValueRange range(TemporalField field)
```

## 参数

此方法接受一个单参数 `field`，该字段是要查询范围的字段。

## 返回值

此方法返回 `ValueRange`，这是该字段的有效值范围，不为空。

## 异常

此方法抛出以下异常：

*   `DateTimeException` – 如果无法获取字段的范围。
*   `UnsupportedTemporalTypeException` – 如果字段不受支持。

下面的程序说明了 `range()` 方法：

## 示例程序

### 程序 1

```java
// Java program to demonstrate
// ChronoLocalDate.range() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD);

        // get range of Days field
        // from ChronoLocalDate using range method
        ValueRange range
            = localD.range(ChronoField.DAY_OF_MONTH);

        // print range of DAY_OF_MONTH
        System.out.println("Range of DAY_OF_MONTH: "
                           + range);
    }
}
```

**输出：**

```java
ChronoLocalDate: 2018-12-06
Range of DAY_OF_MONTH: 1 - 31
```

### 程序 2

```java
// Java program to demonstrate
// ChronoLocalDate.range() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD);

        // get range of DAY_OF_YEAR field
        // from ChronoLocalDate using range method
        ValueRange range
            = localD.range(ChronoField.DAY_OF_YEAR);

        // print range of DAY_OF_YEAR
        System.out.println("Range of DAY_OF_YEAR: "
                           + range);
    }
}
```

**输出：**

```java
ChronoLocalDate: 2018-12-06
Range of DAY_OF_YEAR: 1 - 365
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#range-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#range-java.time.temporal.TemporalField-)