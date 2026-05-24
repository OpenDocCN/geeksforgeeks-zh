# Java 中的 LocalDate adjustInto()方法

> 原文：[https://www.geeksforgeeks.org/localdate-adjustinto-method-in-java/](https://www.geeksforgeeks.org/localdate-adjustinto-method-in-java/)

Java 中 `LocalDate` 类的 `adjustInto()` 方法用于调整指定的时态对象，使其与该对象具有相同的日期。

## 语法

```java
public Temporal adjustInto(Temporal temporal)
```

## 参数

该方法接受单个参数 `temporal`，该参数为需要调整的目标对象，不能为 `null`。

## 返回值

返回调整后的对象，不为 `null`。

## 异常

函数抛出如下所述的两个异常：

1.  `DateTimeException`：当程序无法调整时抛出。
2.  `ArithmeticException`：如果发生数值溢出，程序将抛出此异常。

## 示例程序

下面的程序说明了 Java 中 `LocalDate` 的 `adjustInto()` 方法：

### 程序 1

```java
// Program to illustrate the adjustInto() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        ZonedDateTime date = ZonedDateTime.now();

        // prints the date
        System.out.println(date);

        // Parses the date
        LocalDate date1 = LocalDate.parse("2015-01-31");

        // Uses the function to adjust the date
        date = (ZonedDateTime)date1.adjustInto(date);

        // Prints the adjusted date
        System.out.println(date);
    }
}
```

**输出：**

```java
2018-11-28T05:36:08.205Z[Etc/UTC]
2015-01-31T05:36:08.205Z[Etc/UTC]
```

### 程序 2

举例说明异常。下面的程序抛出一个异常，因为 2 月是 28 天，而不是 31 天。

```java
// Program to illustrate the adjustInto() method
// Exception Program

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        try {
            ZonedDateTime date = ZonedDateTime.now();

            // prints the date
            System.out.println(date);

            // Parses the date
            LocalDate date1 = LocalDate.parse("2015-02-31");

            // Uses the function to adjust the date
            date = (ZonedDateTime)date1.adjustInto(date);

            // Prints the adjusted date
            System.out.println(date);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
2018-11-28T05:36:11.014Z[Etc/UTC]
java.time.format.DateTimeParseException: 
Text '2015-02-31' could not be parsed: Invalid date 'FEBRUARY 31'
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#adjustInto(java.time.temporal.Temporal)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#adjustInto(java.time.temporal.Temporal))