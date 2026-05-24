# Java 中的 LocalDate isAfter()方法，示例

> 原文: [https://www.geeksforgeeks.org/localdate-isafter-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-isafter-method-in-java-with-examples/)

Java 中 `LocalDate` 类的 `isAfter()`方法检查该日期是否在指定日期之后。

## 语法

```java
public boolean isAfter(ChronoLocalDate date2)
```

## 参数

该方法接受单个强制参数 `date2`，即要进行比较的其他日期，不可为空。

## 返回值

如果该日期在指定日期之后，则函数返回 `true`。

下面的程序说明了 Java 中 `LocalDate` 的 `isAfter()`方法：

## 程序 1

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2017-11-27");

        // Checks
        System.out.println(dt1.isAfter(dt2));
    }
}
```

### 输出

```java
true
```

## 程序 2

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2019-11-27");

        // Checks
        System.out.println(dt1.isAfter(dt2));
    }
}
```

### 输出

```java
false
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isAfter(java.time.chrono.ChronoLocalDate)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isAfter(java.time.chrono.ChronoLocalDate))