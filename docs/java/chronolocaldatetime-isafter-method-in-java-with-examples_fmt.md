# Java 中的 ChronoLocalDateTime isAfter()方法，示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-isafter-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-isafter-method-in-java-with-examples/)

Java 中`ChronoLocalDateTime`接口的`isAfter()`方法用于检查作为参数传递的日期是否在该`ChronoLocalDateTime`实例之后。它返回一个布尔值来显示比较结果。

## 语法

```java
default boolean isAfter(ChronoLocalDateTime otherDate)
```

## 参数

该方法接受一个参数`otherDate`，该参数指定要与该时间地点日期时间进行比较的其他日期时间。它不应为`null`。

## 返回

该函数返回`boolean`值，显示该日期时间是否在指定的日期时间之后。

下面的程序说明了`ChronoLocalDateTime.isAfter()`方法：

## 程序 1

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoLocalDateTime dt2
            = LocalDateTime.parse("2016-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isAfter(dt2));
    }
}
```

## 输出

```java
2018-11-03T12:45:30
2016-12-04T12:45:30
true
```

## 程序 2

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoLocalDateTime dt2
            = LocalDateTime.parse("2019-12-04T12:45:30");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isAfter(dt2));
    }
}
```

## 输出

```java
2018-11-03T12:45:30
2019-12-04T12:45:30
false
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isAfter-java.time.chrono.ChronoLocalDateTime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isAfter-java.time.chrono.ChronoLocalDateTime-)