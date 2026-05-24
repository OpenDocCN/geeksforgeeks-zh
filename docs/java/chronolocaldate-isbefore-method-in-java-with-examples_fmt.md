# Java中的ChronoLocalDate isBefore()方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-isbefore-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isbefore-method-in-java-with-examples/)

Java中`ChronoLocalDate`接口的`isBefore()`方法检查该日期是否在指定日期之前，并返回一个表示该结果的布尔值。

## 语法

```java
public boolean isAfter(ChronoLocalDate date2)
```

## 参数

该方法接受单个强制参数`date2`，即要进行比较的其他日期，不可为`null`。

## 返回值

如果该日期在指定日期之前，则函数返回`true`。

## 示例程序

下面的程序说明了Java中的`isBefore()`方法：

### 程序1

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Parses the second date
        ChronoLocalDate dt2
            = LocalDate.parse("2017-11-27");

        // Check if the specified date
        // is before this date
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出：**

```java
false
```

### 程序2

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Parses the second date
        ChronoLocalDate dt2
            = LocalDate.parse("2019-11-27");

        // Check if the specified date
        // is before this date
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出：**

```java
true
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isBefore-java.time.chrono.ChronoLocalDate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isBefore-java.time.chrono.ChronoLocalDate-)