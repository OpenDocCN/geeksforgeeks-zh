# Java 中的 MonthDay getLong()方法，带示例

> 原文：[https://www.geeksforgeeks.org/monthday-getlong-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-getlong-method-in-java-with-examples/)

Java 中 `MonthDay` 类的 `getLong()` 方法将这个 `MonthDay` 的指定字段的值作为 `long` 返回。

## 语法

```java
public long getLong(TemporalField field)
```

## 参数

该方法接受一个参数 `field`，指定该字段为 `long` 且不为空。

## 返回

该函数返回该字段的 `long` 值。

## 异常

该函数抛出如下三个异常：

*   `DateTimeException`：当无法获取此字段的值或该值超出此字段的有效值范围时抛出。
*   `UnsupportedTemporalTypeException`：当字段不受支持或值范围超出 `long` 范围时抛出。
*   `ArithmeticException`：当数值溢出时抛出。

## 示例

下面的程序说明了 `MonthDay.getLong()` 方法：

### 程序 1

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        MonthDay tm1 = MonthDay.parse("--10-12");

        System.out.println(
            tm1.getLong(ChronoField.DAY_OF_MONTH));
    }
}
```

**输出：**

```java
12
```

### 程序 2

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        MonthDay tm1
            = MonthDay.parse("--12-06");
        System.out.println(
            tm1.getLong(
                ChronoField.DAY_OF_MONTH));
    }
}
```

**输出：**

```java
6
```

### 程序 3：演示 DateTimeException

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        try {

            // Parses the date
            MonthDay tm1
                = MonthDay.parse("--13-12");

            System.out.println(
                tm1.getLong(
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
 Text '--13-12' could not be parsed:
 Unable to obtain MonthDay from TemporalAccessor:
 {DayOfMonth=12, MonthOfYear=13},
 ISO of type java.time.format.Parsed
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#getLong-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#getLong-java.time.temporal.TemporalField-)