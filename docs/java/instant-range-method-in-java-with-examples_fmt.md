# Java 中的 Instant.range() 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-range-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-range-method-in-java-with-examples/)

`Instant` 类的 `range()` 方法有助于获取作为参数传递的字段的有效值范围。此方法返回一个 `ValueRange` 对象，该对象包含字段的最小和最大有效值。这个 `Instant` 有助于提高返回范围的准确性。当字段不受支持且方法无法返回范围值时，将引发异常。

## 语法

```java
public ValueRange range(TemporalField field)
```

## 参数

该方法接受一个参数 `field`，该字段是获取取值范围的字段。

## 返回值

此方法返回 `ValueRange`，这是该字段的有效值范围，不为空。

## 异常

如果无法获得字段的范围，此方法将抛出以下异常：

*   `DateTimeException`：如果无法获得字段的范围。
*   `UnsupportedTemporalTypeException`：如果该字段不受支持。

## 示例程序

下面的程序说明了 `range()` 方法：

### 程序 1

```java
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant
        System.out.println("Instant: "
                           + instant);

        // get range of MILLI_OF_SECOND field
        // from instant using range method
        ValueRange range
            = instant.range(ChronoField.MILLI_OF_SECOND);

        // print range of MILLI_OF_SECOND
        System.out.println("Range of MILLI_OF_SECOND: "
                           + range);
    }
}
```

### 程序 2

```java
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant
        System.out.println("Instant: "
                           + instant);

        // get range of NANO_OF_SECOND field
        // from instant using range method
        ValueRange range
            = instant.range(ChronoField.NANO_OF_SECOND);

        // print range of NANO_OF_SECOND
        System.out.println("Range of NANO_OF_SECOND: "
                           + range);
    }
}
```

### 程序 3：获取不支持的 `TemporalField` 异常

```java
// Java program to demonstrate
// Instant.range() method

import java.time.*;
import java.time.temporal.ChronoField;
import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // try to find range of era using ChronoField
        try {

            ValueRange secondvalue
                = instant.range(ChronoField.ERA);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#range(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#range(java.time.temporal.TemporalField))