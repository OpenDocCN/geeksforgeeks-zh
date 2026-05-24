# Java 中的 LocalDate getLong()方法，带示例

> 原文：[https://www.geeksforgeeks.org/localdate-getlong-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-getlong-method-in-java-with-examples/)

Java 中 `LocalDate` 类的 `getLong()`方法得到了在这个日期适用的纪元。

## 语法

```java
public long getLong(TemporalField field)
```

## 参数

该方法接受单个强制参数 `field`，指定要获取的字段，不为空。

## 返回值

该函数返回该字段的值。

## 异常

程序抛出三个异常，描述如下：

1.  **Date and Time Exception**：如果无法获取此字段的值，或者该值超出了此字段的有效范围，将抛出异常。
2.  **UnsupportedTemporalTypeException**：如果此字段不受支持或值的范围超过长整型，将被抛出。
3.  **ArithmeticException**：当数值溢出时抛出。

下面的程序说明了 Java 中 `LocalDate` 的 `getLong()` 方法：

## 程序 1

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(ChronoField.DAY_OF_MONTH));
    }
}
```

**输出：**

```java
27
```

## 程序 2

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(ChronoField.DAY_OF_YEAR));
    }
}
```

**输出：**

```java
331
```

## 程序 3

```java
// Program to illustrate the getLong() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        try {
            LocalDate dt = LocalDate.parse("2017-01-32");
            System.out.println(dt.getLong(ChronoField.DAY_OF_MONTH));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.time.format.DateTimeParseException: Text '2017-01-32' could not be parsed: Invalid value for DayOfMonth (valid values 1 - 28/31): 32
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getLong(java.time.temporal.TemporalField)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getLong(java.time.temporal.TemporalField))