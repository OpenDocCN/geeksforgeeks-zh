# Java 中的 ChronoLocalDateTime.compareTo() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-compareto-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-compareto-method-in-java-with-examples/)

Java 中 `ChronoLocalDateTime` 接口的 `compareTo()` 方法将此日期与另一个日期进行比较。

## 语法

```java
default int compareTo(ChronoLocalDateTime other)
```

## 参数

该方法接受一个参数 `other`，该参数指定要比较的其他日期，并且不能为 `null`。

## 返回值

返回比较值，如果此日期小于另一个日期则为负，大于则为正。

下面的程序说明了 Java 中 `ChronoLocalDateTime` 的 `compareTo()` 方法：

## 程序 1

```java
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-06T19:21:12");
        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");
        System.out.println(dt1);

        try {
            // Compare both dates
            System.out.println(dt1.compareTo(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
2018-12-06T19:21:12
2018-12-06T19:21:12
0
```

## 程序 2

```java
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime.parse("2018-12-05T19:21:12");
        System.out.println(dt);

        // Second date
        ChronoLocalDateTime dt1
            = LocalDateTime.parse("2018-12-06T19:21:12");
        System.out.println(dt1);

        try {
            // Compare both dates
            System.out.println(dt1.compareTo(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
2018-12-05T19:21:12
2018-12-06T19:21:12
1
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#compareTo-java.time.chrono.ChronoLocalDateTime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#compareTo-java.time.chrono.ChronoLocalDateTime-)