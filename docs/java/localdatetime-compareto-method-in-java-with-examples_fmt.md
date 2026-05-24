# Java 中的 LocalDateTime compareTo() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-compareto-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-compareto-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `compareTo()` 方法用于将该日期时间与作为参数传递的日期时间进行比较。

## 语法

```java
public int compareTo(ChronoLocalDateTime anotherDate)
```

## 参数

该方法接受一个参数 `anotherDate`，该参数指定要比较的另一个日期时间。它不应为 `null`。

## 返回

该函数返回一个 `int` 值，这是比较后的比较值。

下面的程序说明了 `LocalDateTime.compareTo()` 方法：

## 程序 1

```java
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2015-01-05T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("After comparison: "
                           + dt2.compareTo(dt1));
    }
}
```

## 输出

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2015-01-05T12:45:30
After comparison: -3
```

## 程序 2

```java
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2010-12-05T12:50:30");

        // Prints the date
        System.out.println("Date 1: " + dt1);

        // Parses the date
        LocalDateTime dt2
            = LocalDateTime
                  .parse("2012-05-10T12:50:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("After comparison: "
                           + dt2.compareTo(dt1));
    }
}
```

## 输出

```java
Date 1: 2010-12-05T12:50:30
Date 2: 2012-05-10T12:50:30
After comparison: 2
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#compareTo(java.time.chrono.ChronoLocalDateTime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#compareTo(java.time.chrono.ChronoLocalDateTime))