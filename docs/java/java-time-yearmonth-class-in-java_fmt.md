# Java 中的 YearMonth 类

> 原文：`https://www.geeksforgeeks.org/java-time-yearmonth-class-in-java/`

Java 的 `YearMonth` 类用于表示“年-月”格式的组合。这是一个不可变类，意味着其对象一旦创建，值就无法更改。可以从年月组合中导出诸如季度等信息。此类不存储或表示日期、时间或时区。例如，它不会显示“11月-2006-12:00”，而是显示“2007-11”。它继承自 `Object` 类并实现了 `Comparable` 接口。

`YearMonth` 类实现了 `Temporal`、`TemporalAdjuster`、`Comparable<YearMonth>` 和 `Serializable` 接口。

```java
public final class YearMonth extends Object
    implements Temporal, TemporalAdjuster, Comparable<YearMonth>, Serializable
```

## 方法列表

| **方法** | **描述** |
| --- | --- |
| `adjustInto(Temporal temporal)` | 将指定的 `Temporal` 对象调整为今年的月份。 |
| `atDay(int dayOfMonth)` | 将年月与月日结合创建一个 `LocalDate`。 |
| `atEndOfMonth()` | 返回月末的 `LocalDate`。 |
| `compareTo(YearMonth other)` | 将今年的月份与另一年的月份进行比较。 |
| `equals(Object object)` | 检查这个 `YearMonth` 是否等于另一个 `YearMonth`。 |
| `format(DateTimeFormatter formatter)` | 使用指定的格式化程序格式化今年的月份。 |
| `from(TemporalAccessor temporal)` | 从 `Temporal` 对象中获取 `YearMonth` 的实例。 |
| `get(TemporalField field)` | 以 `int` 形式获取指定字段的值。 |
| `getLong(TemporalField field)` | 从今年-月开始获取指定字段的值。 |
| `getMonth()` | 使用 `Month` 枚举获取月份字段。 |
| `getMonthValue()` | 获取从 1 到 12 的月份字段值。 |
| `getYear()` | 获取年份字段。 |
| `hashCode()` | 返回此 `YearMonth` 的哈希码。 |
| `isAfter(YearMonth other)` | 检查该年-月是否在指定的年-月之后。 |
| `isBefore(YearMonth other)` | 检查该年-月是否在指定的年-月之前。 |
| `isLeapYear()` | 根据 ISO 日历系统规则，检查年份是否为闰年。 |
| `isSupported(TemporalField field)` | 检查指定的字段是否受支持。 |
| `isSupported(TemporalUnit unit)` | 检查指定的单元是否受支持。 |
| `isValidDay(int dayOfMonth)` | 检查月日是否对此年月有效。 |
| `lengthOfMonth()` | 返回月的长度，同时考虑年。 |
| `lengthOfYear()` | 返回一年的长度。 |
| `minus(long amountToSubtract, TemporalUnit unit)` | 返回减去指定金额后的本年度-月份的副本。 |
| `minus(TemporalAmount amountToSubtract)` | 返回减去指定金额后的本年度-月份的副本。 |
| `minusMonths(long monthsToSubtract)` | 返回减去指定月数后的本年度月的副本。 |
| `minusYears(long yearsToSubtract)` | 返回减去指定年数的本年度月的副本。 |
| `now()` | 从默认时区的系统时钟中获取当前的年-月。 |
| `now(Clock clock)` | 从指定的时钟获取当前的年-月。 |
| `now(ZoneId zone)` | 从指定时区的系统时钟中获取当前的年-月。 |
| `of(int year, int month)` | 从年和月中获取 `YearMonth` 的实例。 |
| `of(int year, Month month)` | 从年和月中获取 `YearMonth` 的实例。 |
| `parse(CharSequence text)` | 从文本字符串（如“2007-12”）中获取 `YearMonth` 的实例。 |
| `parse(CharSequence text, DateTimeFormatter formatter)` | 使用特定的格式化程序从文本字符串中获取 `YearMonth` 的实例。 |
| `plus(long amountToAdd, TemporalUnit unit)` | 返回添加了指定金额的本年度-月份的副本。 |
| `plus(TemporalAmount amountToAdd)` | 返回添加了指定金额的本年度-月份的副本。 |
| `plusMonths(long monthsToAdd)` | 返回添加了指定月数的本年度月的副本。 |
| `plusYears(long yearsToAdd)` | 返回添加了指定年数的本年度月的副本。 |
| `query(TemporalQuery<R> query)` | 使用指定的查询来查询本年度-月份。 |
| `range(TemporalField field)` | 获取指定字段的有效值范围。 |
| `toString()` | 以字符串形式输出今年-月，如“2007-12”。 |
| `until(Temporal endExclusive, TemporalUnit unit)` | 根据指定的单位计算到下一年的时间。 |
| `with(TemporalAdjuster adjuster)` | 返回今年-月的调整副本。 |
| `with(TemporalField field, long newValue)` | 返回指定字段设置为新值的本年度-月份的副本。 |
| `withMonth(int month)` | 返回一份今年月的副本，其中修改了年月。 |
| `withYear(int year)` | 返回一个年月的副本，并更改年份。 |

## 方法实现示例

### 1. `plus()`
返回添加了所需金额的本年度-月份的副本。

```java
// plus() Method implementation
import java.time.*;
public class Example {
    public static void main(String[] args)
    {
        YearMonth obj1 = YearMonth.now();

        // plus(Period.ofYears(int)) will add
        // no.of years to the existing year
        YearMonth obj2 = obj1.plus(Period.ofYears(0));
        System.out.println(obj2);
    }
}
```

**输出**

```java
2021-02
```

### 2. `minus()`
返回减去所需金额后的本年度-月份的副本。

```java
// minus() method implementation
import java.time.*;
public class Example {
    public static void main(String[] args)
    {
        YearMonth obj1 = YearMonth.now();

        //.minus(Period.ofYears(int)) will subtract
        // no. of years from the existing year
        YearMonth obj2 = obj1.minus(Period.ofYears(3));
        System.out.println(obj2);
    }
}
```

**输出**

```java
2018-02
```