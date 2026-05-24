# Java 中的 `LocalDateTime` `isBefore()` 方法示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-isbefore-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-isbefore-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `isBefore()` 方法检查该日期是否在指定的日期时间之前。

**语法：**

```java
public boolean isBefore(ChronoLocalDateTime other)
```

**参数：** 此方法接受一个参数 `other`，它是要比较的另一个日期时间。它不应为 `null`。

**返回：** 如果该日期时间在指定日期时间之前，该函数返回 `boolean` 值。

下面的程序说明了 `LocalDateTime.isBefore()` 方法：

### 程序 1

```java
// Program to illustrate the isBefore() method

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
                  .parse("2016-12-04T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares both dates
        System.out.println("Is Date 1 before Date 2: "
                           + dt1.isBefore(dt2));
    }
}
```

**Output:**

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2016-12-04T12:45:30
Is Date 1 before Date 2: false
```

### 程序 2

```java
// Program to illustrate the isBefore() method

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
                  .parse("2019-12-04T12:45:30");

        // Prints the date
        System.out.println("Date 2: " + dt2);

        // Compares both dates
        System.out.println("Is Date 1 before Date 2: "
                           + dt1.isBefore(dt2));
    }
}
```

**Output:**

```java
Date 1: 2018-11-03T12:45:30
Date 2: 2019-12-04T12:45:30
Is Date 1 before Date 2: true
```

**参考：** [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isBefore(java.time.chrono.ChronoLocalDateTime)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#isBefore(java.time.chrono.ChronoLocalDateTime))