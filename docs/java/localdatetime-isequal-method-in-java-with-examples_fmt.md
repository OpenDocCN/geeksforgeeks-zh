# Java 中的 LocalDateTime isEqual()方法，带示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-isequal-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-isequal-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `isEqual()` 方法用于检查该日期是否等于指定的日期时间。

## 语法

```java
public boolean isEqual(ChronoLocalDateTime other)
```

## 参数

该方法接受一个参数 `other`，该参数指定要比较的其他日期时间。它不应为 `null`。

## 返回

如果该日期时间等于指定的日期时间，则函数返回 `boolean` 值。

下面的程序说明了 `LocalDateTime.isEqual()` 方法：

## 程序 1

```java
// Program to illustrate the isEqual() method

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
                  .parse("2018-11-03T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares the date
        System.out.println("After comparison: "
                           + dt2.isEqual(dt1));
    }
}
```

**输出：**

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2018-11-03T12:45:30
After comparison: true
```

## 程序 2

```java
// Program to illustrate the isEqual() method

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
                           + dt2.isEqual(dt1));
    }
}
```

**输出：**

```java
Date 1: 2010-12-05T12:50:30
Date 2: 2012-05-10T12:50:30
After comparison: false
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isEqual(java.time.chrono.ChronoLocalDateTime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isEqual(java.time.chrono.ChronoLocalDateTime))