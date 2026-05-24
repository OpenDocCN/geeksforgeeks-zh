# Java 中 ChronoPeriod between() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-between-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-between-method-in-java-with-examples/)

Java 中 `ChronoPeriod` 接口的 `between()` 方法用来获取由两个给定日期（包括开始日期和不包括结束日期）之间的年、月、日数组成的计时周期。

该时间周期如下所示：

*   移除整月。
*   现在，计算剩余的天数。
*   然后，进行调整以确保两者具有相同的标志。
*   现在，月数根据每年12个月的规则被划分为年和月。
*   考虑一个月，如果结束日期的月份大于或等于开始日期的月份（例如，从2017年5月12日到2018年7月18日是一年两个月零六天）。

**注意：** 从上面公式得到的计时周期可以是一个*负数*，如果结束在开始之前。负号在每年、每月和每一天都是一样的。

## 语法

```java
static ChronoPeriod between(ChronoLocalDate startDateInclusive,
                            ChronoLocalDate endDateExclusive)
```

## 参数

*   `startDateInclusive` – 开始日期，包含在内，不能为空。
*   `endDateExclusive` – 结束日期，不包含在内，不能为空。

## 返回值

`between()` 函数返回给定开始日期和结束日期之间的 `ChronoPeriod`。

下面是上述功能的实现：

```java
// Java code to show the chronoPeriod
// between the given start and end date

import java.time.*;
import java.time.chrono.*;

public class ChronoPeriodClass {

// Function to calculate chronoPeriod between
    // start and end date
    static void
    calculateChronoPeriod(ChronoLocalDate startDate,
                          ChronoLocalDate endDate)
    {
        ChronoPeriod chronoPeriod
            = ChronoPeriod.between(startDate, endDate);
        System.out.println("ChronoPeriod between start and end "
                           + "date is : " + chronoPeriod);
    }

// Driver Code
    public static void main(String[] args)
    {
        // Start date
        ChronoLocalDate startDate
            = LocalDate.parse("2017-02-13");

        // End date
        ChronoLocalDate endDate
            = LocalDate.parse("2018-08-20");

        calculateChronoPeriod(startDate, endDate);
    }
}
```

## 输出

```java
ChronoPeriod between start and end date is : P1Y6M7D
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#between-java.time.chrono.ChronoLocalDate-java.time.chrono.ChronoLocalDate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#between-java.time.chrono.ChronoLocalDate-java.time.chrono.ChronoLocalDate-)