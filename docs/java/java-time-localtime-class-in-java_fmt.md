# java 中的 java.time.LocalTime 类

> 原文：[https://www.geeksforgeeks.org/java-time-localtime-class-in-java/](https://www.geeksforgeeks.org/java-time-localtime-class-in-java/)

Java 是最流行的编程语言，也是应用最广泛的编程语言。Java 用于各种应用，如移动应用、桌面应用、网络应用。像在 Java 中一样，`java.time.LocalTime` 类表示时间，时间被视为小时-分-秒。这个类是不可变的，也是线程安全的。`java.time.LocalTime` 类下有各种各样的方法，这将在下面解释，实现也将在下面执行。`java.time` 是一个用来处理当前日期和时间 API 的包。

*   导入 `java.time.LocalTime` 等类。
*   现在使用 `LocalTime.now()` 存储当前时间。
*   显示存储在变量中的当前时间。

首先，这个类的大多数方法都以表格的形式展示如下：

| 方法 | 描述 |
| --- | --- |
| `adjustInto(Temporal temporal)` | 将此时间调整为与指定的时间对象相同。 |
| `atDate(LocalDate date)` | 将此时间与日期相结合，创建一个 `LocalDateTime`。 |
| `atOffset(ZoneOffset offset)` | 将此时间与偏移量相结合，创建一个 `OffsetTime`。 |
| `compareTo(LocalTime other)` | 将这次与另一次进行比较。 |
| `equals(Object obj)` | 检查这个时间是否等于另一个时间。 |
| `format(DateTimeFormatter formatter)` | 使用指定的格式化程序格式化这次。 |
| `get(TemporalField field)` | 以 `int` 形式获取指定字段的值。 |
| `getHour()` | 获取一天中的小时字段。 |
| `getMinute()` | 获取分钟字段。 |
| `getNano()` | 获取纳秒字段。 |
| `getSecond()` | 获取秒字段。 |
| `hashCode()` | 这次的哈希代码。 |
| `isAfter(LocalTime other)` | 检查该时间是否在指定时间之后。 |
| `isBefore(LocalTime other)` | 检查该时间是否在指定时间之前。 |
| `isSupported(TemporalField field)` | 检查指定的字段是否受支持。 |
| `minus(long amountToSubtract, TemporalUnit unit)` | 返回减去指定数量后的时间副本。 |
| `minusHours(long hoursToSubtract)` | 返回减去指定小时数后的本地时间副本。 |
| `minusMinutes(long minutesToSubtract)` | 返回减去指定分钟数后的本地时间副本。 |
| `minusNanos(long nanosToSubtract)` | 返回减去指定纳秒数后的本地时间副本。 |
| `minusSeconds(long secondsToSubtract)` | 返回减去指定秒数后的本地时间副本。 |
| `now()` | 从默认时区的系统时钟获取当前时间。 |
| `of(int hour, int minute)` | 从小时和分钟获取 `LocalTime` 的实例。 |
| `ofNanoOfDay(long nanoOfDay)` | 从纳秒日值中获取 `LocalTime` 的实例。 |
| `ofSecondOfDay(long secondOfDay)` | 从一天中的秒值获取 `LocalTime` 的实例。 |
| `parse(CharSequence text)` | 从文本字符串（如 `10:15`）中获取 `LocalTime` 的实例。 |
| `plus(long amountToAdd, TemporalUnit unit)` | 返回添加了指定数量的时间副本。 |
| `plusHours(long hoursToAdd)` | 返回添加了指定小时数的本地时间的副本。 |
| `plusMinutes(long minutesToAdd)` | 返回添加了指定分钟数的本地时间的副本。 |
| `plusNanos(long nanosToAdd)` | 返回添加了指定纳秒数的本地时间的副本。 |
| `plusSeconds(long secondsToAdd)` | 返回添加了指定秒数的本地时间的副本。 |
| `query(TemporalQuery<R> query)` | 这次使用指定的查询进行查询。 |
| `range(TemporalField field)` | 获取指定字段的有效值范围。 |
| `toNanoOfDay()` | 以纳秒为单位提取时间，从 0 到 24 * 60 * 60 * 1,000,000,000 - 1。 |
| `truncatedTo(TemporalUnit unit)` | 返回时间被截断的本地时间的副本。 |
| `with(TemporalAdjuster adjuster)` | 返回此时间的调整副本。 |
| `withHour(int hour)` | 返回更改了一天中某个小时的本地时间的副本。 |
| `withMinute(int minute)` | 返回该本地时间的副本，并更改分钟。 |
| `withNano(int nanoOfSecond)` | 返回该本地时间的副本，更改后的时间为纳秒。 |
| `withSecond(int second)` | 返回该本地时间的副本，更改秒。 |

## 实施

### 例 1

```java
// Java Program to illustrate LocalTime Class

// Importing LocalDateTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String args[]) {

      // Creating an object of LocalTime class by
      // declaring a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

      // Print and display the LocalTime value
        System.out.println("Local time value : "+ltime);       
    }
}
```

**Output**

```
Local time value : 06:20:52.986897
```

### 例 2

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

    // main driver method
    public static void main(String args[])
    {
        // Creating an object of LocalTime Class by
        // declaring a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

      // Now plusMinute() will add up minutes to the LocalTime
        LocalTime time3 = ltime.plusMinutes(120);

        // Display the time using object of class
        System.out.println("Time : "+time3);
    }
}
```

**Output**

```
Time : 08:34:59.135137
```

### 例 3

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

   // Main class
    public static void main(String args[])
    {
        // Creating an object of LocalTime class by
        // declare a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

        // plusHours() method will add up Hours to
        // the LocalTime
        LocalTime time3 = ltime.plusHours(05);

        // Display the time
        System.out.println(time3);
    }
}
```

**Output**

```
17:48:53.003478
```

### 例 4

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // creating an object of. LocalTime Class by
        // declare a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

        // minusMinute() will subtract minutes from
        // the LocalTime
        LocalTime time = ltime.minusMinutes(120);

        // Display the time
        System.out.println(time);
    }
}
```

**Output**

```
10:54:49.649675
```