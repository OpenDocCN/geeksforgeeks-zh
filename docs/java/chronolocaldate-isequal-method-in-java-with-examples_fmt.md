# Java 中的 ChronoLocalDate isEqual() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-isequal-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isequal-method-in-java-with-examples/)

Java 中 `ChronoLocalDate` 接口的 `isEqual()` 方法检查该日期是否等于指定日期。

## 语法

```java
public boolean isEqual(ChronoLocalDate date2)
```

## 参数

该方法接受单个强制参数 `date2`，即要进行比较的其他日期，不可为 `null`。

## 返回值

如果该日期等于指定日期，则函数返回 `true`。

## 程序 1

下面的程序说明了 Java 中的 `isEqual()` 方法：

```java
// Program to illustrate the isEqual() method

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
            = LocalDate.parse("2018-11-27");

        // Check if these two are equal
        System.out.println(dt1.isEqual(dt2));
    }
}
```

输出：

```java
true
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
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Parses the second date
        ChronoLocalDate dt2
            = LocalDate.parse("2015-11-27");

        // Check if these two are equal
        System.out.println(dt1.isEqual(dt2));
    }
}
```

输出：

```java
false
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isEqual-java.time.chrono.ChronoLocalDate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isEqual-java.time.chrono.ChronoLocalDate-)