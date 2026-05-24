# Java 程序以上午-下午格式格式化时间

> 原文：[https://www.geeksforgeeks.org/java-program-to-format-time-in-am-pm-format/](https://www.geeksforgeeks.org/java-program-to-format-time-in-am-pm-format/)

`日期时间类格式`用于显示日期和时间，并在 Java 中操作日期和时间。除此之外，它还用于在 Java 中格式化跨时区关联数据的日期和时间类。所以为了从名为 `java.utils` 的包中导入这个类。导入该类后，可以创建 `Date` 类的对象，以便打印当前日期和时间。现在，为了打印默认的日期和时间，只需使用 `toString()` 方法调用打印命令来获取当前的日期和时间。

如果从代码基引用中的任何时间通过内置数据类函数调用计算，毫秒数设置为 1970 年 1 月 1 日。为了打印到目前为止的毫秒数，只需使用 `getTime()` 而不是 `toString()` 来获取到目前为止的毫秒数。假设用户想要从特定日期、时间和月份到当前时间。这可以通过 Java 的 `Date` 和 `SimpleDateFormat` 类来实现。

> **注：** 纪元时间 1970 年 1 月 1 日

**方法：**

*   使用 `SimpleDateFormat`
*   使用拆分字符串

## 方法 1：`SimpleDateFormat`

`SimpleDateFormat` 类是 Java 中的一个类，提供了几种解析和格式化日期和时间的方法。这个类继承了 `DateFormat` 类。Java 中 `DateFormat` 类的 `format()` 方法，用于将给定日期格式化为日期/时间字符串。基本上，该方法用于将该日期和时间转换为特定格式，即“mm/dd/yyyy”。`format()` 用于以特定方式更改给它的参数格式的方法。

**语法：**

```java
public final String format(Date date)
```

**参数：** 该方法取 `Date` 对象类型的一个参数 `date`，指的是要产生字符串输出的日期。

**返回值：** 该方法以“mm/dd/yyyy”的字符串格式返回日期或时间。

**实现：** 在这个 Java 示例中，用户输入的时间由 24 点转换为 12 小时格式，带有 AM/PM 标记。

### Java 代码示例

```java
// Java program to convert 24 hour
// time format to 12 hour format

// Importing specific date class libraries
import java.util.Date;
import java.text.SimpleDateFormat;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the current current time
        Date date = new Date();

        System.out.println("Current Time is : " + date);

        // set format in 12 hours
        SimpleDateFormat formatTime = new SimpleDateFormat("hh.mm aa");
        // hh = hours in 12hr format
        // mm = minutes
        // aa = am/pm

        String time = formatTime.format(
            date); // changing the format of 'date'

        // display time as per format
        System.out.println(
            "Current Time in AM/PM Format is : " + time);
    }
}
```

**输出**

```java
Current Time is : Mon Oct 26 08:34:53 UTC 2020
Current Time in AM/PM Format is : 08.34 AM
```