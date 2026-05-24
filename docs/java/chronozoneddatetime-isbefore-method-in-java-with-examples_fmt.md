# Java 中的 ChronoZonedDateTime isBefore() 方法

> 原文：[https://www.geeksforgeeks.org/chronozoneddatetime-isbefore-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-isbefore-method-in-java-with-examples/)

Java 中 `ChronoZonedDateTime` 接口的 `isBefore()` 方法用于检查作为参数传递的日期是否在该 `ChronoZonedDateTime` 实例之前。它返回一个布尔值，显示比较结果。

## 语法

```java
public boolean isBefore(ChronoZonedDateTime otherDate)
```

## 参数

该方法接受一个参数 `otherDate`，该参数指定要与该 `ChronoZonedDateTime` 进行比较的其他日期时间。它不应为 `null`。

## 返回值

函数返回 `boolean` 值，显示该日期时间是否在指定的日期时间之前。

## 示例

下面的程序说明了 `ChronoZonedDateTime.isBefore()` 方法：

### 程序 1

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoZonedDateTime dt2
            = ZonedDateTime.parse(
                "2018-10-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出：**

```java
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
2018-10-06T19:21:12.123+05:30[Asia/Calcutta]
false
```

### 程序 2

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoZonedDateTime dt1
            = ZonedDateTime.parse(
                "2018-10-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt1);

        // Parses the date
        ChronoZonedDateTime dt2
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // Prints the date
        System.out.println(dt2);

        // Compares both dates
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出：**

```java
2018-10-06T19:21:12.123+05:30[Asia/Calcutta]
2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
true
```

## 参考资料

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#isBefore-java.time.chrono.ChronoZonedDateTime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#isBefore-java.time.chrono.ChronoZonedDateTime-)