# Java 中带有 withDayOfMonth() 方法的 LocalDate 示例

> 原文：[https://www.geeksforgeeks.org/localdate-withdayofmonth-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-withdayofmonth-method-in-java-with-examples/)

Java 中 `LocalDate` 类的 `withDayOfMonth()` 方法返回一个更改了月日的 `LocalDate` 的副本。

## 语法

```java
public LocalDate withDayOfMonth(int dayOfMonth)
```

## 参数

该方法接受一个强制参数 `dayOfMonth`，在结果中设置一个月中的哪一天，从 1 到 28-31。

## 返回值

该函数根据请求日期返回一个本地日期，不为空。

## 异常

当月日值无效时，函数抛出 `DateTimeException`。

下面的程序说明了 `LocalDate.withDayOfMonth()` 方法：

### 程序 1

```java
// Program to illustrate the withDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        LocalDate dt1 = LocalDate.parse("2018-12-07");
        LocalDate result = dt1.withDayOfMonth(01);

        // Prints the date with year
        System.out.println("The date with day of the month is: " + result);
    }
}
```

**输出：**

```java
The date with day of the month is: 2018-12-01
```

### 程序 2

```java
// Program to illustrate the withDayOfMonth() method
// Exceptions
import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        try {
            // Parses the date
            LocalDate dt1 = LocalDate.parse("2018-12-07");
            LocalDate result = dt1.withDayOfMonth(35);

            // Prints the date with year
            System.out.println("The date with day of the month is: " + result);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.time.DateTimeException: Invalid value for DayOfMonth (valid values 1 - 28/31): 35
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#withDayOfMonth(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#withDayOfMonth(int))