# Java 中的 `java.time.Period` 类

> 原文：[https://www.geeksforgeeks.org/java-time-period-class-in-java/](https://www.geeksforgeeks.org/java-time-period-class-in-java/)

Java 中的 `Period` 类用于获取以年、月、日为单位的时间量或时间跨度。获得的时间是 ISO-8601 日历系统中基于日期的时间量，例如“4 年、5 个月和 6 天”。`Period` 中支持的单位是年、月和日。所有这三个字段始终存在，但可以设置为零。

**语法：类声明**

```java
public final class Period 
extends Object 
implements ChronoPeriod, Serializable
```

以下所有方法及其执行的操作以表格形式列出：

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| `addTo(Temporal temporal)` | 此方法将此 `Period` 添加到指定的时间对象中。 |
| `between(LocalDate startDateInclusive, LocalDate endDateExclusive)` | 此方法获取由两个日期之间的年数、月数和天数组成的 `Period`。 |
| `equals(Object object)` | 此方法检查此 `Period` 是否等于另一个 `Period`。 |
| `from(TemporalAmount amount)` | 此方法从时间量中获取 `Period` 的实例。 |
| `get(TemporalUnit unit)` | 此方法获取请求单位的值。 |
| `getChronology()` | 此方法得到此 `Period` 的年表，就是 ISO 日历系统。 |
| `getDays()` | 此方法获取此 `Period` 的天数。 |
| `getMonths()` | 此方法获取此 `Period` 的月数。 |
| `getUnits()` | 此方法获取此 `Period` 支持的单位集。 |
| `getYears()` | 此方法获取此 `Period` 的年数。 |
| `hashCode()` | 此方法返回此 `Period` 的哈希代码。 |
| `isNegative()` | 此方法检查此 `Period` 的三个单位中是否有任何一个是负数。 |
| `isZero()` | 此方法检查此 `Period` 的所有三个单位是否都为零。 |
| `minus(TemporalAmount amountToSubtract)` | 此方法返回减去指定时间量后的该 `Period` 的副本。 |
| `minusDays(long daysToSubtract)` | 此方法返回减去指定天数的该 `Period` 的副本。 |
| `minusMonths(long monthsToSubtract)` | 此方法返回减去指定月份后的该 `Period` 的副本。 |
| `minusYears(long yearsToSubtract)` | 此方法返回减去指定年份后的该 `Period` 的副本。 |
| `multipliedBy(int scalar)` | 此方法返回一个新实例，该实例中的每个元素都乘以指定的标量。 |
| `negated()` | 此方法返回一个新实例，该实例中的每个时间量都被否定。 |
| `normalized()` | 此方法返回此 `Period` 的副本，其中年和月是标准化的。 |
| `of(int years, int months, int days)` | 此方法获取一个代表年、月和日的 `Period`。 |
| `ofDays(int days)` | 此方法获取一个表示天数的 `Period`。 |
| `ofMonths(int months)` | 此方法获取一个表示月数的 `Period`。 |
| `ofWeeks(int weeks)` | 此方法获取一个代表周数的 `Period`。 |
| `ofYears(int years)` | 此方法获得一个代表年数的 `Period`。 |
| `parse(CharSequence text)` | 此方法从文本字符串（如 `PnYnMnD`）中获取 `Period`。 |
| `plus(TemporalAmount amountToAdd)` | 此方法返回添加了指定时间量的该 `Period` 的副本。 |
| `plusDays(long daysToAdd)` | 此方法返回添加了指定天数的此 `Period` 的副本。 |
| `plusMonths(long monthsToAdd)` | 此方法返回添加了指定月份的该 `Period` 的副本。 |
| `plusYears(long yearsToAdd)` | 此方法返回添加了指定年份的该 `Period` 的副本。 |
| `subtractFrom(Temporal temporal)` | 此方法从指定的时间对象中减去此 `Period`。 |
| `toString()` | 此方法将此 `Period` 输出为字符串，如 `P6Y3M1D`。 |
| `toTotalMonths()` | 此方法获取此 `Period` 的总月数。 |
| `withDays(int days)` | 此方法返回指定天数的此 `Period` 的副本。 |
| `withMonths(int months)` | 此方法返回指定月数的此 `Period` 的副本。 |
| `withYears(int years)` | 此方法返回具有指定年数的此 `Period` 的副本。 |

</figure>

让我们实现这个类的一些方法。

## 示例 1

```java
// Java program to illustrate Period class
// demonstrate the methods of this class
// Methods - minus() and ofMonths()

// Importing Period class from
// java.time package
import java.time.Period;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Obtaining period representing number of months
        // using ofMonths() method by
        // creating object of period class
        Period p1 = Period.ofMonths(6);

        // minus() will return a copy of this period
        // with the specified period subtracted.
        Period p2 = p1.minus(Period.ofMonths(2));

        // Print and display on the console
        System.out.println(p2);
    }
}
```

**输出**

```java
P4M
```

让我们举另一个例子来讨论更多的方法。

### 方法 1：`ofDays()`

此类方法用于从给定的天数中获取一个 `Period` 作为参数。

**语法：**

```java
public static Period ofDays(int numberOfDays)
```

**参数：** 该方法接受单个参数 `numberOfDays`，即解析成 `Period` 对象的天数。

**返回：** 该函数返回 `Period`，该 `Period` 是用给定天数解析的 `Period` 对象。

### 方法 2：`addTo()`

这个类的 `addTo()` 方法将这个 `Period` 添加到特定的时态对象中。

**语法：**

```java
public Temporal addTo(Temporal temporal)
```

**参数：** 要调整的时态对象 `temporal` 不应为空。

**返回类型：** 进行了调整的同类型对象。

**异常：** 该方法引发 `DateTimeException` 和 `ArithmeticException`。

## 示例 2

```java
// Java program to illustrate Period class
// demonstrate the methods of this class
// Methods like ofDays() and addTo()

// Importing all classes from java.time package
import java.time.*;
import java.time.temporal.Temporal;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting a period representing number of days
        // using ofDays() method
        Period p = Period.ofDays(24);

        // Adding this period to the
        // temporal object i.e. temp
        Temporal temp = p.addTo(LocalDate.now());

        // Print and display on the console
        System.out.println(temp);
    }
}
```

**输出**

```java
2021-03-29
```