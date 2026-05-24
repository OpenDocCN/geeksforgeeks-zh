# Java 中的 ChronoLocalDateTime.isEqual() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-isequal-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-isequal-method-in-java-with-examples/)

Java 中 `ChronoLocalDateTime` 接口的 `isEqual()` 方法用来检查作为参数传递的日期是否等于这个 `ChronoLocalDateTime` 实例。它返回一个显示相同内容的布尔值。

## 语法

```java
public boolean isEqual(ChronoLocalDateTime otherDate)
```

## 参数

该方法接受一个参数 `otherDate`，该参数指定要与该时间地点日期时间进行比较的其他日期时间。它不应为 `null`。

## 返回

该函数返回 `boolean` 值，显示该日期时间是否等于指定的日期时间。

下面的程序说明了 `ChronoLocalDateTime.isEqual()` 方法：

## 程序 1

```java
// Program to illustrate the isEqual() method

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
        System.out.println(dt1.isEqual(dt2));
    }
}
```

## 输出

```java
2018-11-03T12:45:30
2016-12-04T12:45:30
false
```

## 程序 2

```java
// Program to illustrate the isEqual() method

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
        System.out.println(dt1.isEqual(dt2));
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

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isEqual-java.time.chrono.ChronoLocalDateTime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#isEqual-java.time.chrono.ChronoLocalDateTime-)