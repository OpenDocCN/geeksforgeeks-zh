# Java 程序计算两个时间段的差值

> 原文：[https://www.geeksforgeeks.org/java-program-to-calculate-difference-between-two-time-periods/](https://www.geeksforgeeks.org/java-program-to-calculate-difference-between-two-time-periods/)

在本文中，让我们探索各种方法来找出 Java 中两个时间段之间的区别。为简单起见，我们假设提供给我们的时间段的格式为 `HH:MM:SS`。

## 示例

## 方法 1：使用 SimpleDateFormat 类和 Date 类

`SimpleDateFormat` 类已经被添加到第 7 个 JDK 版本的 `java.text` 包中。通过创建简单日期格式对象，解析格式为 `HH:MM:SS` 的时间段。`SimpleDateFormat` 对象解析时间段并返回一个日期对象，该对象可用于计算经过的时间。

下面是上述方法的代码：

```java
// Java Program to Find the difference
// between Two Time Periods

// Importing the Date Class from the util package
import java.util.*;

// Importing the SimpleDateFormat
// Class from the text package
import java.text.*;

public class GFG {

    public static void main(String[] args) throws Exception
    {
        // Dates to be parsed
        String time1 = "18:00:00";
        String time2 = "7:30:50";

        // Creating a SimpleDateFormat object
        // to parse time in the format HH:MM:SS
        SimpleDateFormat simpleDateFormat
            = new SimpleDateFormat("HH:mm:ss");

        // Parsing the Time Period
        Date date1 = simpleDateFormat.parse(time1);
        Date date2 = simpleDateFormat.parse(time2);

        // Calculating the difference in milliseconds
        long differenceInMilliSeconds
            = Math.abs(date2.getTime() - date1.getTime());

        // Calculating the difference in Hours
        long differenceInHours
            = (differenceInMilliSeconds / (60 * 60 * 1000))
              % 24;

        // Calculating the difference in Minutes
        long differenceInMinutes
            = (differenceInMilliSeconds / (60 * 1000)) % 60;

        // Calculating the difference in Seconds
        long differenceInSeconds
            = (differenceInMilliSeconds / 1000) % 60;

        // Printing the answer
        System.out.println(
            "Difference is " + differenceInHours + " hours "
            + differenceInMinutes + " minutes "
            + differenceInSeconds + " Seconds. ");
    }
}
```

**输出**

**时间复杂度:** O(1)

## 方法 2：使用 LocalTime 和 ChronoUnit 类

Java 在第 8 个 JDK 版本中带来了大量的特性，其中很少是 `java.time` 包中的 `LocalTime` 和 `ChronoUnit` 类。`LocalTime` 对象解析格式为 `HH:MM:SS` 的日期，而 `ChronoUnit` 用于获取小时、分钟和秒的差值。

下面是上述方法的代码：

```java
// Java program to get the difference
// between Two Time Periods in Java

// Importing the LocalTime class
import java.time.*;

// Importing the ChronoUnit class
import java.time.temporal.ChronoUnit;

class GFG {
    public static void main(String[] args)
    {
        // Parsing Time Period in the format HH:MM:SS
        LocalTime time1 = LocalTime.of(18, 00, 00);
        LocalTime time2 = LocalTime.of(21, 22, 00);

        // Calculating the difference in Hours
        long hours = ChronoUnit.HOURS.between(time1, time2);

        // Calculating the difference in Minutes
        long minutes
            = ChronoUnit.MINUTES.between(time1, time2) % 60;

        // Calculating the difference in Seconds
        long seconds
            = ChronoUnit.SECONDS.between(time1, time2) % 60;

        // Printing the difference
        System.out.println(
            "Difference is " + hours + " hours " + minutes
            + " minutes " + seconds + " seconds.");
    }
}
```

**输出**

**时间复杂度:** O(1)