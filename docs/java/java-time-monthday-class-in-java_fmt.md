# java 中的 java.time.MonthDay 类

> 原文：[https://www.geeksforgeeks.org/java-time-monthday-class-in-java/](https://www.geeksforgeeks.org/java-time-monthday-class-in-java/)

Java 是最流行的编程语言，也是应用最广泛的编程语言。Java 用于各种应用，如移动应用、桌面应用、网络应用。`java.time.MonthDay` 类表示一个月中的月和日的组合，并且是不可变的。`java.time` 是一个用来处理当前日期和时间 API 的包。下面以表格的形式讨论了这个类的所有方法。

| 方法 | 描述 |
| --- | --- |
| `adjust(Temporal)` | 将指定的时态对象调整为有这个月日。 |
| `atYear(int year)` | 将这个月日和一年结合起来，创建一个 `LocalDate`。 |
| `compareTo(MonthDay other)` | 将本月日与另一个月日进行比较。 |
| `format(DateTimeFormatter formatter)` | 使用指定的格式化程序格式化这个月-日。 |
| `getDayOfMonth()` | 获取当月的日字段。 |
| `getMonth()` | 使用 `Month` 枚举获取年月字段。 |
| `getMonthValue()` | 获取从 1 到 12 的年月字段。 |
| `hashCode()` | 本月-日的一个 hash 码。 |
| `isAfter(MonthDay other)` | 检查此月-日是否在指定的月-日之后。 |
| `now()` | 从默认时区的系统时钟获取当前的月-日。 |
| `now(Clock clock)` | 从指定的时钟获取当前的月-日。 |
| `of(int month, int dayOfMonth)` | 获取 `MonthDay` 的一个实例。 |
| `query(TemporalQuery<R> query)` | 使用指定查询查询本月-日。 |
| `range(TemporalField field)` | 获取指定字段的有效值范围。 |
| `toString()` | 将本月日作为字符串输出，如--12-03。 |
| `with(Month month)` | 返回本月日的副本，其中年月日已更改。 |
| `withDayOfMonth(int dayOfMonth)` | 返回该月日的副本，其中更改了月日。 |
| `withMonth(int month)` | 返回该月的副本，其中更改了年月日。 |

**实现：** 现在我们来讨论一下这个类的几个方法

*   导入类和包 `java.time`。
*   现在使用像 `MonthDay.of()` 或其他任何方法，并存储一个 `MonthDay` 的实例。
*   显示变量中存储的值。

**例 1**

```java
// Java Program to illustrate MonthDay Class

// Importing Month and MonthDay classes
// from java.time package
import java.time.Month;
import java.time.MonthDay;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of MonthDay class by
        // storing instance of MonthDay by
        // passing date and month as arguments

        // Custom inputs are passed as arguments
        MonthDay monthday = MonthDay.of(Month.MARCH, 14);

        // Print and display the value stored
        System.out.println(monthday);
    }
}
```

**输出**

```java
--03-14
```

**例 2**

```java
// Java Program to illustrate MonthDay Class

// importing MonthDay class from java.time
import java.time.MonthDay;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Store an instance of MonthDay
        // from a text i.e --03-14
        MonthDay monthday = MonthDay.parse("--03-14");

        // Display the month using instance of class
        System.out.println(monthday.getMonth());
    }
}
```

**输出**

```java
MARCH
```