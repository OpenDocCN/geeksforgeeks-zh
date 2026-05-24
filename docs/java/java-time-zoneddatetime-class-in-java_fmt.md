# ZonedDateTime 类

> 原文：[https://www.geeksforgeeks.org/java-time-zoneddatetime-class-in-java/](https://www.geeksforgeeks.org/java-time-zoneddatetime-class-in-java/)

`ZonedDateTime` 是一个不可变的对象，代表日期时间和时区。此类存储所有日期和时间字段。这个类存储精确到纳秒的时间和一个时区，用一个区域偏移量来处理本地日期时间。例如，值“2011 年 10 月 2 日亚洲/加尔各答时区 14:45.30.123456789 +05:30”可以存储在 `ZonedDateTime` 中。此类还用于将本地日期时间的本地时间线转换为即时的即时时间线。

## 类别申报

```java
public final class ZonedDateTime
extends Object
implements Temporal, ChronoZonedDateTime<LocalDate>, Serializable
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [`equals(Object object)`](https://www.geeksforgeeks.org/zoneddatetime-equals-method-in-java-with-examples/) | 此方法检查此日期时间是否等于另一个日期时间。 |
| [`format(DateTimeFormatter formatter)`](https://www.geeksforgeeks.org/zoneddatetime-format-method-in-java-with-examples/) | 此方法使用指定的格式化程序格式化此日期时间。 |
| [`from(Temporal temporal)`](https://www.geeksforgeeks.org/zoneddatetime-form-method-in-java-with-examples/) | 此方法从时态对象中获取 `ZonedDateTime` 的实例。 |
| [`get(TemporalField field)`](https://www.geeksforgeeks.org/zoneddatetime-get-method-in-java-with-examples/) | 此方法从该日期时间获取指定字段的值作为 `int`。 |
| [`getDayOfMonth()`](https://www.geeksforgeeks.org/zoneddatetime-getdayofmonth-method-in-java-with-examples/) | 此方法获取月中的某一天字段。 |
| [`getDayOfWeek()`](https://www.geeksforgeeks.org/zoneddatetime-getdayofweek-method-in-java-with-examples/) | 此方法获取星期几字段，这是一个枚举 `DayOfWeek`。 |
| [`getDayOfYear()`](https://www.geeksforgeeks.org/zoneddatetime-getdayofyear-method-in-java-with-examples/) | 此方法获取年中的某一天字段。 |
| [`getHour()`](https://www.geeksforgeeks.org/zoneddatetime-gethour-method-in-java-with-examples/) | 此方法获取一天中的小时字段。 |
| [`getLong(TemporalField field)`](https://www.geeksforgeeks.org/zoneddatetime-getlong-method-in-java-with-examples/) | 此方法从该日期时间中获取指定字段的值作为长整型。 |
| [`getMinute()`](https://www.geeksforgeeks.org/zoneddatetime-getminute-method-in-java-with-examples/) | 此方法获取分钟/小时字段。 |
| [`getMonth()`](https://www.geeksforgeeks.org/zoneddatetime-getmonth-method-in-java-with-examples/) | 此方法使用月份枚举获取年度月份字段。 |
| [`getMonthValue()`](https://www.geeksforgeeks.org/zoneddatetime-getmonthvalue-method-in-java-with-examples/) | 此方法获取从 1 到 12 的年月字段。 |
| `getNano()` | 这种方法可以得到纳米秒的磁场。 |
| `getOffset()` | 此方法获取区域偏移量，如“+01:00”。 |
| `getSecond()` | 此方法获取分钟秒字段。 |
| [`getYear()`](https://www.geeksforgeeks.org/zoneddatetime-getyear-method-in-java-with-examples/) | 此方法获取年份字段。 |
| `getZone()` | 此方法获取时区，如“欧洲/巴黎”。 |
| [`hashCode()`](https://www.geeksforgeeks.org/zoneddatetime-hashcode-method-in-java-with-examples/) | 此日期时间的哈希代码。 |
| [`isSupported(TemporalField field)`](https://www.geeksforgeeks.org/zoneddatetime-issupported-method-in-java-with-examples/) | 此方法检查指定的字段是否受支持。 |
| [`isSupported(TemporalUnit unit)`](https://www.geeksforgeeks.org/zoneddatetime-issupported-method-in-java-with-examples/) | 此方法检查指定的单元是否受支持。 |
| [`minus(long amountToSubtract, TemporalUnit unit)`](https://www.geeksforgeeks.org/zoneddatetime-minus-method-in-java-with-examples/) | 此方法返回减去指定金额后的日期时间副本。 |
| [`minus(TemporalAmount amountToSubtract)`](https://www.geeksforgeeks.org/zoneddatetime-minus-method-in-java-with-examples/) | 此方法返回减去指定金额后的日期时间副本。 |
| [`minusDays(long days)`](https://www.geeksforgeeks.org/zoneddatetime-minusdays-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的天数。 |
| [`minusHours(long hours)`](https://www.geeksforgeeks.org/zoneddatetime-minushours-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的小时数。 |
| [`minusMinutes(long minutes)`](https://www.geeksforgeeks.org/zoneddatetime-minusminutes-method-in-java-with-examples/) | 此方法返回该区域的副本，减去指定的分钟数。 |
| [`minusMonths(long months)`](https://www.geeksforgeeks.org/zoneddatetime-minusmonths-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的月数。 |
| [`minusNanos(long nanos)`](https://www.geeksforgeeks.org/zoneddatetime-minusnanos-method-in-java-with-examples/) | 此方法返回此 `ZonedDateTime` 的副本，并减去指定的纳秒数。 |
| [`minusSeconds(long seconds)`](https://www.geeksforgeeks.org/zoneddatetime-minusseconds-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的秒数。 |
| [`minusWeeks(long weeks)`](https://www.geeksforgeeks.org/zoneddatetime-minusweeks-method-in-java-with-examples/) | 此方法返回该区域的副本，减去指定的周数。 |
| [`minusYears(long years)`](https://www.geeksforgeeks.org/zoneddatetime-minusyears-method-in-java-with-examples/) | 此方法返回该区域的副本，并减去指定的年数。 |
| [`now()`](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从默认时区的系统时钟获取当前日期时间。 |
| [`now(Clock clock)`](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从指定的时钟获取当前日期时间。 |
| [`now(ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-now-method-in-java-with-examples/) | 此方法从指定时区的系统时钟获取当前日期时间。 |
| [`of(int year, int month, int day, int hour, int minute, int second, int nano, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从年、月、日、小时、分钟、秒、纳秒和时区获取 `ZonedDateTime` 的实例。 |
| [`of(LocalDate date, LocalTime time, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从本地日期和时间获取 `ZonedDateTime` 的实例。 |
| [`of(LocalDateTime localDateTime, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/) | 此方法从本地日期时间获取 `ZonedDateTime` 的实例。 |
| [`ofInstant(Instant instant, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-ofinstant-class-in-java-with-examples/) | 此方法从即时获取 `ZonedDateTime` 的实例。 |
| [`ofInstant(LocalDateTime localDateTime, ZoneOffset offset, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-ofinstant-class-in-java-with-examples/) | 此方法从通过组合本地日期时间和偏移量形成的瞬间获取 `ZonedDateTime` 的实例。 |
| [`ofLocal(LocalDateTime localDateTime, ZoneId zone, ZoneOffset preferredOffset)`](https://www.geeksforgeeks.org/zoneddatetime-oflocal-method-in-java-with-examples/) | 如果可能，此方法使用首选偏移量从本地日期时间获取 `ZonedDateTime` 的实例。 |
| [`ofStrict(LocalDateTime localDateTime, ZoneOffset offset, ZoneId zone)`](https://www.geeksforgeeks.org/zoneddatetime-ofstrict-method-in-java-with-examples/) | 此方法获取一个严格验证本地日期时间、偏移量和区域标识组合的区域数据时间实例。 |
| `parse(CharSequence text)` | 此方法从文本字符串(如 `2007-12-03T10:15:30+01:00[Europe/Paris]`)中获取 `ZonedDateTime` 的实例 |
| [`parse(CharSequence text, DateTimeFormatter formatter)`](https://www.geeksforgeeks.org/zoneddatetime-parse-method-in-java-with-examples/) | 此方法使用特定的格式化程序从文本字符串中获取 `ZonedDateTime` 的实例。 |
| [`plus(long amountToAdd, TemporalUnit unit)`](https://www.geeksforgeeks.org/zoneddatetime-plus-method-in-java-with-examples/) | 此方法返回添加了指定金额的日期时间的副本。 |
| [`plus(TemporalAmount amountToAdd)`](https://www.geeksforgeeks.org/zoneddatetime-plus-method-in-java-with-examples/) | 此方法返回添加了指定金额的日期时间的副本。 |
| [`plusDays(long days)`](https://www.geeksforgeeks.org/zoneddatetime-plusdays-method-in-java-with-examples/) | 此方法返回添加了指定天数的此 `ZonedDateTime` 的副本。 |
| [`plusHours(long hours)`](https://www.geeksforgeeks.org/zoneddatetime-plushours-method-in-java-with-examples/) | 此方法返回添加了指定小时数的此 `ZonedDateTime` 的副本。 |
| `plusMinutes(long minutes)` | 此方法返回添加了指定分钟数的此 `ZonedDateTime` 的副本。 |
| [`plusMonths(long months)`](https://www.geeksforgeeks.org/zoneddatetime-plusmonths-method-in-java-with-examples/) | 此方法返回添加了指定月数的此 `ZonedDateTime` 的副本。 |
| `plusNanos(long nanos)` | 此方法返回添加了指定纳秒数的此 `ZonedDateTime` 的副本。 |

# ZonedDateTime 方法参考

## 方法列表

| 方法 | 描述 |
| --- | --- |
| `plusSeconds(long seconds)` | 此方法返回添加了指定秒数的此 `ZonedDateTime` 的副本。 |
| `plusWeeks(long weeks)` | 此方法返回添加了指定周数的此 `ZonedDateTime` 的副本。 |
| `plusYears(long years)` | 此方法返回添加了指定年数的此 `ZonedDateTime` 的副本。 |
| `query(TemporalQuery<R> query)` | 此方法使用指定的查询来查询此日期时间。 |
| `range(TemporalField field)` | 此方法获取指定字段的有效值范围。 |
| `toLocalDate()` | 此方法获取此日期时间的 `LocalDate` 部分。 |
| `toLocalDateTime()` | 此方法获取此日期时间的本地日期时间部分。 |
| `toLocalTime()` | 这个方法获取这个日期时间的 `LocalTime` 部分。 |
| `toOffsetDateTime()` | 此方法将此日期时间转换为 `OffsetDateTime`。 |
| `toString()` | 此方法将此日期时间输出为字符串，例如 `2007-12-03T10:15:30+01:00[Europe/Paris]`。 |
| `truncatedTo(TemporalUnit unit)` | 此方法返回时间被截断的该区域的副本。 |
| `until(Temporal endExclusive, TemporalUnit unit)` | 此方法根据指定的单位计算到另一个日期时间的时间量。 |
| `with(TemporalAdjuster adjuster)` | 此方法返回此日期时间的调整副本。 |
| `with(TemporalField field, long newValue)` | 此方法返回此日期时间的副本，并将指定字段设置为新值。 |
| `withDayOfMonth(int dayOfMonth)` | 此方法返回更改了月中某一天的 `ZonedDateTime` 的副本。 |
| `withDayOfYear(int dayOfYear)` | 此方法返回一个更改了日期的 `ZonedDateTime` 副本。 |
| `withEarlierOffsetAtOverlap()` | 此方法返回此日期时间的副本，将区域偏移更改为本地时间线重叠处两个有效偏移中较早的一个。 |
| `withFixedOffsetZone()` | 此方法返回此日期时间的副本，并将区域标识设置为偏移量。 |
| `withHour(int hour)` | 此方法返回一个更改了一天中某个小时的 `ZonedDateTime` 的副本。 |
| `withLaterOffsetAtOverlap()` | 此方法返回此日期时间的副本，将区域偏移更改为本地时间线重叠处两个有效偏移中的较晚者。 |
| `withMinute(int minute)` | 此方法返回此 `ZonedDateTime` 的副本，其中更改了分钟/小时。 |
| `withMonth(int month)` | 此方法返回此 `ZonedDateTime` 的副本，其中更改了年月日。 |
| `withNano(int nanoOfSecond)` | 此方法返回一个更改了纳米秒的 `ZonedDateTime` 的副本。 |
| `withSecond(int second)` | 此方法返回此 `ZonedDateTime` 的副本，更改了分钟的秒数。 |
| `withYear(int year)` | 此方法返回一个更改了年份的 `ZonedDateTime` 的副本。 |
| `withZoneSameInstant(ZoneId zone)` | 此方法返回具有不同时区的此日期时间的副本，保留即时消息。 |
| `withZoneSameLocal(ZoneId zone)` | 此方法返回具有不同时区的此日期时间的副本，如果可能，保留本地日期时间。 |

## parse() 方法的实现

以下是一个使用 `parse()` 方法创建新 `ZonedDateTime` 的 Java 程序示例。

```java
// java program to create a new
// ZonedDateTime using parse() method
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";
        // creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);
        System.out.println(zone);
    }
}
```

**输出**

```java
2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]
```

## getZone() 方法的实现

以下是一个说明 `getZone()` 方法工作的 Java 程序示例。

```java
// java program to illustrate working of getZone() method
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";

        // Creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);

        // printing the zone of this zonedDateTime object
        System.out.println(zone.getZone());
    }
}
```

**输出**

```java
Asia/Kolkata
```

## plus() 和 minus() 方法的实现

以下是一个说明 `plus()` 和 `minus()` 方法工作的 Java 程序示例。

```java
// java program to illustrate working
// of plus() and minus() method
import java.time.Period;
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        String text
            = "2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]";

        // Creating a new ZonedDateTime object
        ZonedDateTime zone = ZonedDateTime.parse(text);

        // printing original value of
        // this ZonedDateTime object
        System.out.println(zone);
        // printing value of this ZonedDateTime
        // object after substracing two months
        System.out.println(zone.minus(Period.ofMonths(2)));
        // printing value of this ZonedDateTime
        // object after adding two months
        System.out.println(zone.plus(Period.ofMonths(2)));
    }
}
```

**输出**

```java
2011-10-02T14:45:30.123456789+05:30[Asia/Kolkata]
2011-08-02T14:45:30.123456789+05:30[Asia/Kolkata]
2011-12-02T14:45:30.123456789+05:30[Asia/Kolkata]
```

## of() 方法的实现

以下是一个说明 `of()` 方法工作的 Java 程序示例。

```java
// Java program to illustrate working of of() method
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class GFG {

    public static void main(String[] args)
    {
        // getting current date
        LocalDate date = LocalDate.now();

        // getting current time
        LocalTime time = LocalTime.now();

        // getting system default zone id
        ZoneId zoneId = ZoneId.systemDefault();

        // creating a new ZonedDateTime object
        ZonedDateTime zonedatetime
            = ZonedDateTime.of(date, time, zoneId);
        System.out.println(zonedatetime);
    }
}
```

**输出**

```java
2021-03-20T17:09:56.241560Z[Etc/UTC]
```