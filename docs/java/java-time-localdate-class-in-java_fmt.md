# java 中的 java.time.LocalDate 类

> 原文: [https://www.geeksforgeeks.org/java-time-localdate-class-in-java/](https://www.geeksforgeeks.org/java-time-localdate-class-in-java/)

[Java](https://www.geeksforgeeks.org/java/) 是目前最流行的编程语言，也是应用最广泛的编程语言。Java 应用于各种应用，如移动应用、桌面应用、网络应用。在这个 Java 中 [`java.time.LocalDate`](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/) 类被导入，表示显示当前日期。

## java.time 包

`java.time` 包是用来和当前日期时间 API 一起工作的包。

## 类

| 类 | 描述 |
| --- | --- |
| `LocalDate` | 这是一个表示日期的类。 |
| `DateTimeFormatter` | 它是一个用于格式化和解析日期和时间的类。 |

## 方法

| 方法 | 描述 |
| --- | --- |
| `adjustInto(Temporal temporal)` | 此方法将指定的时态对象调整为与此对象具有相同的日期。 |
| `atStartOfDay()` | 此方法将此日期与午夜时间相结合，在此日期开始时创建一个 `LocalDateTime`。 |
| `atStartOfDay(ZoneId zone)` | 此方法根据时区中的规则，从最早有效时间的该日期返回 `ZonedDateTime`。 |
| `atTime(int hour, int minute)` | 此方法将此日期和时间结合起来创建一个 `LocalDateTime`。 |
| `atTime(int hour, int minute, int second)` | 此方法将此日期和时间结合起来创建一个 `LocalDateTime`。 |
| `compareTo(ChronoLocalDate other)` | 此方法将此日期与另一个日期进行比较。 |
| `equals(Object object)` | 此方法检查此日期是否等于另一个日期。 |
| `format(DateTimeFormatter formatter)` | 此方法使用指定的格式化程序格式化此日期。 |
| `from(TemporalAccessor temporal)` | 此方法从时态对象中获取 `LocalDate` 的实例。 |
| `get(TemporalField field)` | 此方法从该日期开始以 `int` 形式获取指定字段的值。 |
| `getChronology()` | 此方法获取此日期的年表，即 ISO 日历系统。 |
| `getDayOfMonth()` | 此方法获取月中的某一天字段。 |
| `getDayOfWeek()` | 此方法获取星期几字段，这是一个枚举 `DayOfWeek`。 |
| `getDayOfYear()` | 此方法获取年中的某一天字段。 |
| `getEra()` | 此方法获取在此日期适用的纪元。 |
| `getLong(TemporalField field)` | 此方法从该日期获取指定字段的值作为长整型。 |
| `getMonth()` | 此方法使用月份枚举获取年度月份字段。 |
| `getMonthValue()` | 此方法获取从 1 到 12 的年月字段。 |
| `getYear()` | 此方法获取年份字段。 |
| `hashCode()` | 此日期的哈希代码。 |
| `isAfter(ChronoLocalDate other)` | 此方法检查此日期是否在指定日期之后。 |
| `isBefore(ChronoLocalDate other)` | 此方法检查该日期是否在指定日期之前。 |
| `isEqual(ChronoLocalDate other)` | 此方法检查该日期是否等于指定日期。 |
| `isLeapYear()` | 根据国际标准化组织日历系统规则，此方法检查年份是否为闰年。 |
| `isSupported(TemporalField field)` | 此方法检查指定的字段是否受支持。 |
| `lengthOfMonth()` | 此方法返回由该日期表示的月份长度。 |
| `lengthOfYear()` | 此方法返回由该日期表示的年份长度。 |
| `now()` | 这是一个用于返回 `LocalDateTime` 类实例的方法。 |
| `ofPattern()` | 这是一个与 `DateTimeFormatter` 一起使用的方法，用于格式化和解析日期和时间。它接受所有类型或种类的值，以不同的格式显示。 |
| `query(TemporalQuery<R> query)` | 此方法使用指定的查询来查询此日期。 |
| `range(TemporalField field)` | 此方法获取指定字段的有效值范围。 |
| `toEpochDay()` | 此方法将此日期转换为纪元日。 |
| `withDayOfMonth(int dayOfMonth)` | 此方法返回一份更改了月日的 `LocalDate`。 |
| `withDayOfYear(int dayOfYear)` | 此方法返回一份更改了日期的 `LocalDate` 的副本。 |
| `withMonth(int month)` | 此方法返回一个 `LocalDate` 的副本，其中更改了年月日。 |
| `withYear(int year)` | 此方法返回一个更改了年份的 `LocalDate` 的副本。 |

## 用法

1.  用 `java.time` 包导入 `java.time.LocalDateTime` 和 `java.time.format.DateTimeFormatter` 等类。
2.  请使用 `LocalDateTime.now()` 和 `now()` 方法。
3.  使用 `DateTimeFormatter.ofPattern` 对当前日期进行排序。
4.  显示变量中存储的日期。

下面是问题陈述的实现:

## 示例 1

```java
// import package used to work with current date and time
// api.
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class GFG {

    public static void main(String[] args)
    {
        // now() is a method to return the
        // instance of LocalDateTime class.
        LocalDateTime localDate = LocalDateTime.now();
        // DateTimeFormatter class used to format and
        // parse date and time. ofPattern() is a method
        // used with DateTimeFormatter to format and
        // parse date and time.
        DateTimeFormatter dateformatter
            = DateTimeFormatter.ofPattern("MM dd, YYYY");
        // display the date
        System.out.println(dateformatter.format(localDate));
    }
}
```

**输出**

```java
03 16, 2021
```

## 示例 2

```java
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class GFG {

    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt1 = LocalDate.parse("2021-01-07");
        LocalDate result = dt1.withDayOfYear(01);

        // Prints the date with year
        System.out.println("The date with day of year is: "
                           + result);
    }
}
```

**输出**

```java
The date with day of year is: 2021-01-01
```