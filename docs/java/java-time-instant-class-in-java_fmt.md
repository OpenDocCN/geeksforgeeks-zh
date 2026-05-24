# Java 中的 Instant 类

> 原文：[https://www.geeksforgeeks.org/java-time-instant-class-in-java/](https://www.geeksforgeeks.org/java-time-instant-class-in-java/)

在 Java 语言中，`Instant` 类用于表示当前时间轴上的特定时间瞬间。`Instant` 类扩展了 `Object` 类，实现了 `Temporal`、`TemporalAdjuster`、`Comparable<Instant>` 和 `Serializable` 接口。

## Instant 类声明

```java
public final class Instant extends Object    
implements Temporal, TemporalAdjuster, Comparable<Instant>, Serializable  
```

## 类的字段

| 字段 | 描述 |
| --- | --- |
| `EPOCH` | 1970-01-01T00:00:00Z 纪元瞬间的常数。 |
| `MAX` | 支持的最大 `Instant`，“+10000000000-12-31T23:59:59.999999999Z”。 |
| `MIN` | 支持的最小 `Instant`，“-1000000000-01-01T00:00:00Z”。 |

## 该类方法

| 方法 | 描述 |
| --- | --- |
| `adjustInto(Temporal temporal)` | 此方法调整指定的时间对象以具有这一瞬间。 |
| `atOffset(ZoneOffset offset)` | 这个方法将这个瞬间和一个偏移量结合起来，创建一个 `OffsetDateTime`。 |
| `atZone(ZoneId zone)` | 这个方法将这个瞬间和一个时区结合起来创建一个 `ZonedDateTime`。 |
| `compareTo(Instant otherInstant)` | 此方法将此瞬间与指定的瞬间进行比较。 |
| `equals(Object otherInstant)` | 此方法检查该瞬间是否等于指定的瞬间。 |
| `from(TemporalAccessor temporal)` | 此方法从时态对象获取 `Instant` 的实例。 |
| `get(TemporalField field)` | 此方法以 `int` 形式获取当前指定字段的值。 |
| `getEpochSecond()` | 此方法从 1970-01-01T00:00:00Z 的 Java 纪元中获取秒数。 |
| `getLong(TemporalField field)` | 此方法从此时开始获取指定字段的值。 |
| `getNano()` | 这个方法从第二个开始获取纳秒数，稍后沿着时间线。 |
| `hashCode()` | 此方法返回当前时刻的哈希代码。 |
| `isAfter(Instant otherInstant)` | 此方法检查该时刻是否在指定时刻之后。 |
| `isBefore(Instant otherInstant)` | 此方法检查该时刻是否在指定时刻之前。 |
| `isSupported(TemporalField field)` | 此方法检查指定的字段是否受支持。 |
| `isSupported(TemporalUnit unit)` | 此方法检查指定的单元是否受支持。 |
| `minus(long amountToSubtract, TemporalUnit unit)` | 此方法返回减去指定数量后的该瞬间的副本。 |
| `minus(TemporalAmount amountToSubtract)` | 此方法返回减去指定数量后的该瞬间的副本。 |
| `minusMillis(long millisToSubtract)` | 此方法返回此瞬间的副本，并减去以毫秒为单位的指定持续时间。 |
| `minusNanos(long nanosToSubtract)` | 此方法返回此瞬间的副本，并减去以纳秒为单位的指定持续时间。 |
| `minusSeconds(long secondsToSubtract)` | 此方法返回该瞬间的副本，并减去以秒为单位的指定持续时间。 |
| `now()` | 该方法从系统时钟获得当前时刻。 |
| `now(Clock clock)` | 此方法从指定的时钟获取当前时刻。 |
| `ofEpochMilli(long epochMilli)` | 此方法使用 1970-01-01T00:00:00Z 纪元中的毫秒获取 `Instant` 的实例。 |
| `ofEpochSecond(long epochSecond)` | 此方法使用 1970-01-01T00:00:00Z 的纪元中的秒来获取 `Instant` 的实例。 |
| `ofEpochSecond(long epochSecond, long nanoAdjustment)` | 此方法使用 1970-01-01T00:00:00Z 的历元和纳秒级的秒来获取 `Instant` 的实例。 |
| `parse(CharSequence text)` | 此方法从文本字符串（如 `2007-12-03T10:15:30.00Z`）中获取 `Instant` 的实例。 |
| `plus(long amountToAdd, TemporalUnit unit)` | 此方法返回添加了指定数量的即时副本。 |
| `plus(TemporalAmount amountToAdd)` | 此方法返回添加了指定数量的即时副本。 |
| `plusMillis(long millisToAdd)` | 此方法返回此瞬间的副本，并添加以毫秒为单位的指定持续时间。 |
| `plusNanos(long nanosToAdd)` | 此方法返回此瞬间的副本，并添加以纳秒为单位的指定持续时间。 |
| `plusSeconds(long secondsToAdd)` | 此方法返回此瞬间的副本，并添加以秒为单位的指定持续时间。 |
| `query(TemporalQuery<R> query)` | 此方法使用指定的查询来查询该时刻。 |
| `range(TemporalField field)` | 此方法获取指定字段的有效值范围。 |
| `toEpochMilli()` | 此方法将此瞬间转换为从 1970-01-01T00:00:00Z 的纪元开始的毫秒数。 |
| `toString()` | 使用国际标准化组织 8601 表示法的本瞬间的字符串表示法。 |
| `truncatedTo(TemporalUnit unit)` | 此方法返回被截断为指定单位的即时副本。 |
| `until(Temporal endExclusive, TemporalUnit unit)` | 该方法根据指定的单位计算到另一个时刻的时间。 |
| `with(TemporalAdjuster adjuster)` | 此方法返回此瞬间的调整副本。 |
| `with(TemporalField field, long newValue)` | 此方法返回指定字段设置为新值的该时刻的副本。 |

## 示例

下面的示例显示了与类相关联的不同方法是如何工作的。

```java
import java.time.*;
import java.time.temporal.*;
public class GFG {
    public static void main(String[] args)
    {
        // Parsing a string sequence to Instant
        Instant inst1 = Instant.parse("2021-02-09T11:19:42.12Z");
        System.out.println("Parsed instant is " + inst1);

        // Using isSupported() method to check whether the
        // specified field is supported or not
        System.out.println(inst1.isSupported(ChronoUnit.DAYS));
        System.out.println(inst1.isSupported(ChronoUnit.YEARS));

        // Using Instant.now() to get current instant
        Instant cur = Instant.now();
        System.out.println("Current Instant is " + cur);

        // Using minus() method to find instant value after
        // subtraction
        Instant diff = inst1.minus(Duration.ofDays(70));
        System.out.println("Instant after subtraction : "+ diff);

        // Using plus() method to find instant value after
        // addition
        Instant sum = inst1.plus(Duration.ofDays(10));
        System.out.println("Instant after addition : "+ sum);
    }
}
```

**Output**

```
Parsed instant is 2021-02-09T11:19:42.120Z
true
false
Current Instant is 2021-03-03T16:27:54.378693Z
Instant after subtraction : 2020-12-01T11:19:42.120Z
Instant after addition : 2021-02-19T11:19:42.120Z
```