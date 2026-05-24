# Java 中的 java.time.Duration 类

> 原文：`https://www.geeksforgeeks.org/java-time-duration-class-in-java/`

持续时间是 Java 时间库中基于值的类。它用于获取基于时间的时间量。这个类是不可变的和线程安全的。本文描述了这个类中的所有方法以及一些使用类方法的基本例子。

这个类实现了 `Serializable`、`Comparable<Duration>`、`TemporalAmount` 接口。

## 字段

| 字段 | 描述 |
| --- | --- |
| `static Duration ZERO` | 它是零持续时间的常数。 |

## 方法

| 方法 | 描述 |
| --- | --- |
| `abs()` | 此方法返回长度的正副本 |
| `addTo(Temporal temporal)` | 此方法将此持续时间添加到指定的时间对象中。 |
| `between(Temporal startInclusive, Temporal endExclusive)` | 该方法查找两个时态对象之间的持续时间。 |
| `compareTo(Duration otherDuration)` | 此方法将此持续时间与指定的持续时间进行比较。 |
| `dividedBy(long divisor)` | 此方法返回该持续时间除以指定值的副本。 |
| `equals(Object otherDuration)` | 此方法检查该持续时间是否等于指定的持续时间。 |
| `from(TemporalAmount amount)` | 此方法从时间量中获取持续时间的实例。 |
| `get(TemporalUnit unit)` | 此方法获取请求单位的值。 |
| `getNano()` | 此方法获取持续时间内每秒的纳秒数。 |
| `getSeconds()` | 此方法获取此持续时间内的秒数。 |
| `getUnits()` | 此方法获取此持续时间支持的单位集。 |
| `hashCode()` | 这段时间的哈希代码。 |
| `isNegative()` | 此方法检查该持续时间是否为负，不包括零。 |
| `isZero()` | 此方法检查该持续时间是否为零长度。 |
| `minus(Duration duration)` | 此方法返回该持续时间的副本，并减去指定的持续时间。 |
| `minus(long amountToSubtract, TemporalUnit unit)` | 此方法返回该持续时间的副本，并减去指定的持续时间。 |
| `minusDays(long daysToSubtract)` | 此方法返回此持续时间的副本，减去标准 24 小时天数中的指定持续时间。 |
| `minusHours(long hoursToSubtract)` | 此方法返回该持续时间的副本，并减去以小时为单位的指定持续时间。 |
| `minusMillis(long millisToSubtract)` | 此方法返回此持续时间的副本，并减去以毫秒为单位的指定持续时间。 |
| `minusMinutes(long minutesToSubtract)` | 此方法返回此持续时间的副本，并减去指定的持续时间(以分钟为单位)。 |
| `minusNanos(long nanosToSubtract)` | 此方法返回此持续时间的副本，并减去以纳秒为单位的指定持续时间。 |
| `minusSeconds(long secondsToSubtract)` | 此方法返回此持续时间的副本，并减去以秒为单位的指定持续时间。 |
| `multipliedBy(long multiplicand)` | 此方法返回此持续时间乘以标量的副本。 |
| `negated()` | 此方法返回该持续时间的副本，长度为负。 |
| `of(long amount, TemporalUnit unit)` | 此方法获取一个表示以指定单位表示的金额的持续时间。 |
| `ofDays(long days)` | 此方法获得一个表示标准 24 小时天数的持续时间。 |
| `ofHours(long hours)` | 此方法获取表示标准小时数的持续时间。 |
| `ofMillis(long millis)` | 此方法获取表示毫秒数的持续时间。 |
| `ofMinutes(long minutes)` | 此方法获取表示标准分钟数的持续时间。 |
| `ofNanos(long nanos)` | 此方法获取表示纳秒数的持续时间。 |
| `ofSeconds(long seconds)` | 此方法获取表示秒数的持续时间。 |
| `ofSeconds(long seconds, long nanoAdjustment)` | 此方法获取表示秒数的持续时间和以纳秒为单位的调整。 |
| `parse(CharSequence text)` | 此方法从文本字符串(如 `PnDTnHnMn.nS`)中获取持续时间 |
| `plus(Duration duration)` | 此方法返回添加了指定持续时间的该持续时间的副本。 |
| `plus(long amountToAdd, TemporalUnit unit)` | 此方法返回添加了指定持续时间的该持续时间的副本。 |
| `plusDays(long daysToAdd)` | 此方法返回此持续时间的副本，并添加以标准 24 小时为单位的指定持续时间。 |
| `plusHours(long hoursToAdd)` | 此方法返回此持续时间的副本，并添加以小时为单位的指定持续时间。 |
| `plusMillis(long millisToAdd)` | 此方法返回此持续时间的副本，并添加以毫秒为单位的指定持续时间。 |
| `plusMinutes(long minutesToAdd)` | 此方法返回此持续时间的副本，并添加以分钟为单位的指定持续时间。 |
| `plusNanos(long nanosToAdd)` | 此方法返回此持续时间的副本，并添加以纳秒为单位的指定持续时间。 |
| `plusSeconds(long secondsToAdd)` | 此方法返回此持续时间的副本，并添加以秒为单位的指定持续时间。 |
| `subtractFrom(Temporal temporal)` | 此方法从指定的时间对象中减去此持续时间。 |
| `toDays()` | 此方法获取此持续时间内的天数。 |
| `toHours()` | 此方法获取此持续时间内的小时数。 |
| `toMillis()` | 此方法将此持续时间转换为总长度(毫秒)。 |
| `toMinutes()` | 此方法获取此持续时间内的分钟数。 |
| `toNanos()` | 此方法将此持续时间转换为以纳秒为单位的总长度，表示为长。 |
| `toString()` | 此持续时间的字符串表示形式，使用基于 ISO-8601 秒的表示形式，例如 `PT8H6M12.345S` |
| `withNanos(int nanoOfSecond)` | 此方法以指定的纳米秒返回此持续时间的副本。 |
| `withSeconds(long seconds)` | 此方法以指定的秒数返回此持续时间的副本。 |

## 示例 1

这个示例说明了 `Duration` 类的简单使用。

```java
// Importing required classes
import java.time.Duration;
import java.time.LocalTime;
import java.time.temporal.ChronoUnit;

public class GFG {
   public static void main(String[] args) {

// Initializing Duration variable
      Duration duration = Duration.between(LocalTime.NOON,LocalTime.MIDNIGHT);

// Printing difference between time in seconds
      System.out.println(duration.get(ChronoUnit.SECONDS));

// Finiding absolute difference
      Duration absDuration = duration.abs();

// Printing absolute time difference in seconds
      System.out.println(absDuration.get(ChronoUnit.SECONDS));   
   }
}
```

**Output**

```java

```

## 示例 2

```java
// Importing required classes
import java.time.Duration;
import java.time.temporal.ChronoUnit;

public class GFG {
   public static void main(String[] args) {

// Getting duration in an hour
      Duration duration = Duration.from(ChronoUnit.HOURS.getDuration());

// Printing duration in minutes
      System.out.println(duration.toMinutes());
   }
}
```

**输出:**

```java

```