# 以(MMM)格式显示月份名称的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-display-name-of-a-month-in-mmm-format/](https://www.geeksforgeeks.org/java-program-to-display-name-of-a-month-in-mmm-format/)

Java 是一种最强大的编程语言，通过它我们可以做很多事情，Java 是一种行业首选语言。所以它有一个巨大的功能领域。这里我们讨论一下 Java 的一个最好的特性，那就是我们如何用简短的形式或者 `MMM` 格式来表示月。

## 使用某些类有两种方法可以做到这一点

### 方法一：使用 `SimpleDateFormat` 和 `Date` 类

- 这里，`Date` 类提供当前日期和时间，而 `SimpleDateFormat` 类使用特定格式格式化日期，月份将以 `MMM` 格式显示。
- `SimpleDateFormat` 类位于 Java 的 `text` 包下，而 `Date` 类位于 Java 的 `util` 包下。`Date` 构造函数使用**当前日期和时间**初始化对象。
- `SimpleDateFormat` 是一个用于格式化和解析日期的类。

**示例**

```java
// Java Program to format the date in MMM
// format using SimpleDateFormat() method

import java.util.Date;
import java.text.SimpleDateFormat;
public class GFG {
    public static void main(String args[])
    {
        // initialize Date class
        Date date = new Date();

        // initialize SimpleDateFormat class
        // it accepts the format of date
        // here it accepts the "MMM" format for month
        SimpleDateFormat month = new SimpleDateFormat("MMM");

        // "format" use to format the date in to string
        String currentMonth = month.format(date);

        System.out.println(currentMonth);
    }
}
```

**输出**

```java
Nov
```