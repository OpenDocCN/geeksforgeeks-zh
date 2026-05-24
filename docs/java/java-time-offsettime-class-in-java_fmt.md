# java 中的 java.time.OffsetTime 类

> 原文: [https://www.geeksforgeeks.org/java-time-offsettime-class-in-java/](https://www.geeksforgeeks.org/java-time-offsettime-class-in-java/)

Java `OffsetTime` 类是一个不可变的日期-时间对象，它表示时间，通常被视为小时-分-秒偏移。`OffsetTime` 类表示在 ISO-8601 日历系统中从 UTC/格林威治时间偏移的时间，例如 `18:30:45+08:00`，通常被视为小时-分-秒偏移。这个类是不可变的和线程安全的，存储所有的时间字段，精度为纳秒，以及区域偏移量。

语法：类声明

```java
public final class OffsetTime extends Object   
implements Temporal, TemporalAdjuster, Comparable<OffsetTime>, Serializable  
```

现在让我们来看看收集这类方法知识的主要方法，如下表所示：

| 方法 | 已执行的操作 |
| --- | --- |
| `format(DateTimeFormatter formatter)` | 使用指定的格式化程序格式化这次。 |
| `of(LocalTime time, ZoneOffset offset)` | 从本地时间和偏移量获取偏移量实例。 |
| `range(TemporalField field)` | 获取指定字段的有效值范围。 |
| `toLocalTime()` | 获取此日期时间的本地时间部分。 |
| `with(TemporalAdjuster adjuster)` | 调整指定的时间对象，使其具有与该对象相同的偏移和时间。 |
| `atDate(LocalDate date)` | 将此时间与日期结合起来，创建一个偏移日期时间。 |
| `compareTo(OffsetTime other)` | 将这个偏移时间与另一个时间进行比较。 |
| `equals(Object object)` | 检查这个时间是否等于另一个时间。 |
| `format(DateTimeFormatter formatter)` | 使用指定的格式化程序格式化这次。 |
| `from(TemporalAccessor temporal)` | 从时态对象中获取 `OffsetTime` 的实例。 |
| `get(TemporalField field)` | 以 `int` 形式获取指定字段的值。 |
| `getHour()` | 获取一天中的小时字段。 |
| `getLong(TemporalField field)` | 从此时开始获取指定字段的值，作为长整型。 |
| `getMinute()` | 获取分钟字段。 |
| `getNano()` | 获取纳米秒字段。 |
| `getOffset()` | 获取区域偏移量，如 `+01:00`。 |
| `getSecond()` | 获取分钟秒字段。 |
| `hashCode()` | 这次的哈希代码。 |
| `isAfter(OffsetTime other)` | 检查该偏移时间的瞬间是否在指定时间的瞬间之后，将两个时间应用于一个共同的日期。 |
| `isBefore(OffsetTime other)` | 检查该偏移时间的瞬间是否在指定时间的瞬间之前，将两个时间应用于一个共同的日期。 |
| `isEqual(OffsetTime other)` | 检查该偏移时间的瞬间是否等于指定时间的瞬间，将两个时间应用于一个共同的日期。 |
| `isSupported(TemporalField field)` | 检查指定的字段是否受支持。 |
| `isSupported(TemporalUnit unit)` | 检查是否支持指定的单元。 |
| `minus(long amountToSubtract, TemporalUnit unit)` | 返回减去指定金额后的时间副本。 |
| `minus(TemporalAmount amountToSubtract)` | 返回减去指定金额后的时间副本。 |
| `minusHours(long hours)` | 返回减去指定小时数后的偏移量副本。 |
| `minusMinutes(long minutes)` | 返回减去指定分钟数后的偏移量副本。 |
| `minusNanos(long nanoseconds)` | 返回减去指定纳秒数的偏移量副本。 |
| `minusSeconds(long seconds)` | 返回减去指定秒数后的偏移量副本。 |
| `now()` | 从默认时区的系统时钟获取当前时间。 |
| `now(Clock clock)` | 从指定的时钟获取当前时间。 |
| `now(ZoneId zone)` | 从指定时区的系统时钟获取当前时间。 |
| `of(int hour, int minute, int second, int nanosecond, ZoneOffset offset)` | 从小时、分钟、秒和纳秒中获取偏移时间的实例。 |
| `of(LocalTime time, ZoneOffset offset)` | 从本地时间和偏移量获取偏移量实例。 |
| `ofInstant(Instant instant, ZoneId zone)` | 从即时和区域标识获取偏移时间的实例。 |
| `parse(CharSequence text)` | 从文本字符串(如 `10:15:30+01:00`)中获取 `OffsetTime` 的实例。 |
| `parse(CharSequence text, DateTimeFormatter formatter)` | 使用特定的格式化程序从文本字符串中获取 `OffsetTime` 的实例。 |
| `plus(long amountToAdd, TemporalUnit unit)` | 返回添加了指定金额的时间副本。 |
| `plus(TemporalAmount amountToAdd)` | 返回添加了指定金额的时间副本。 |
| `plusHours(long hours)` | 返回添加了指定小时数的偏移量副本。 |
| `plusMinutes(long minutes)` | 返回添加了指定分钟数的偏移量副本。 |
| `plusNanos(long nanoseconds)` | 返回添加了指定纳秒数的偏移量副本。 |
| `plusSeconds(long seconds)` | 返回添加了指定秒数的偏移量副本。 |
| `query(TemporalQuery<R> query)` | 这次使用指定的查询进行查询。 |
| `range(TemporalField field)` | 获取指定字段的有效值范围。 |
| `toLocalTime()` | 获取此日期时间的本地时间部分。 |
| `toString()` | 以字符串形式输出此时间，例如 `10:15:30+01:00`。 |
| `truncatedTo(TemporalUnit unit)` | 返回时间被截断的偏移量的副本。 |
| `until(Temporal endExclusive, TemporalUnit unit)` | 根据指定的单位计算到另一个时间的时间。 |
| `with(TemporalAdjuster adjuster)` | 返回这次调整后的副本。 |
| `with(TemporalField field, long newValue)` | 返回此时间的副本，并将指定字段设置为新值。 |
| `withHour(int hour)` | 返回一份更改了一天中某个小时的偏移量。 |
| `withMinute(int minute)` | 返回一份更改了分钟的偏移时间。 |
| `withNano(int nanoOfSecond)` | 返回一份这个偏移时间的副本，更改了几分之一秒。 |
| `withOffsetSameInstant(ZoneOffset offset)` | 用指定的偏移量返回该偏移量的副本，确保结果在隐含的一天的同一时刻。 |
| `withOffsetSameLocal(ZoneOffset offset)` | 用指定的偏移量返回该偏移量的副本，确保结果是相同的本地时间。 |
| `withSecond(int second)` | 返回一份更改了第二分钟的偏移时间。 |

现在让我们实现上面表格中列出的一些方法，以深入了解这些方法在内部是如何工作的。

### 示例 1: `now()` 方法

```java
// Java Program to Implement OffsetTime class
// via now() method

// Importing required classes
import java.time.OffsetTime;
import java.time.temporal.ChronoField;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of class in main() method
        OffsetTime offset = OffsetTime.now();

        int h = offset.get(ChronoField.HOUR_OF_DAY);
        System.out.println(h);

        int m = offset.get(ChronoField.MINUTE_OF_DAY);
        System.out.println(m);

        int s = offset.get(ChronoField.SECOND_OF_DAY);
        System.out.println(s);
    }
}
```

**输出**

```java

```

### 示例 2: `getHour()` 方法

```java
// Java Program to Implement OffsetTime Class
// via getHour() method

// Importing the class from java.time package
import java.time.OffsetTime;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of class and
        // operation now() method over it to
        // get the current time from clock
        OffsetTime offset = OffsetTime.now();

        // Getting the hour of day field
        int h = offset.getHour();

        // Print and display the hours
        System.out.println(h + " hours");
    }
}
```

**输出**

```java
4 hours
```

### 示例 3: `getMinute()` 方法

```java
// Java Program to Implement OffsetTime Class
// via getMinute() Method

// Importing the class from java.time package
import java.time.OffsetTime;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of the class
        OffsetTime offset = OffsetTime.now();

        // Getting the minutes of the day field
        int m = offset.getMinute();

        // Print and display the minutes
        System.out.println(m + " minutes");
    }
}
```

**输出**

```java
12 minutes
```