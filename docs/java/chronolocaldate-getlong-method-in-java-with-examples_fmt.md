# Java 中的 ChronoLocalDate getLong()方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-getlong-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-getlong-method-in-java-with-examples/)

Java 中`ChronoLocalDate`接口的`getLong()`方法得到该日期适用的纪元。

## 语法

```java
public long getLong(TemporalField field)
```

## 参数

该方法接受单个强制参数`field`，指定要获取的字段，不为空。

## 返回值

该函数返回该字段的值。

## 异常

程序抛出三个异常，描述如下：

1.  `DateTimeException`：如果无法获取此字段的值，或者该值超出了此字段的有效范围，则会抛出异常。
2.  `UnsupportedTemporalTypeException`：如果此字段不受支持，或者值的范围超过了长整型，则会抛出异常。
3.  `ArithmeticException`：当数值溢出时抛出。

## 示例

下面的程序说明了 Java 中的`getLong()`方法：

### 程序 1

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(
            ChronoField.DAY_OF_MONTH));
    }
}
```

**输出：**

```java

```

### 程序 2

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(
            ChronoField.DAY_OF_YEAR));
    }
}
```

**输出：**

```java

```

### 程序 3

```java
// Program to illustrate the getLong() method
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
                = LocalDate.parse("2017-01-32");
            System.out.println(dt.getLong(
                ChronoField.DAY_OF_MONTH));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.time.format.DateTimeParseException:
 Text '2017-01-32' could not be parsed:
 Invalid value for DayOfMonth (valid values 1 - 28/31): 32
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#getLong-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#getLong-java.time.temporal.TemporalField-)