# Java 中的 ChronoPeriod addTo() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-addto-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-addto-method-in-java-with-examples/)

`java.time.chrono` 包中 `ChronoPeriod` 接口的 `addTo()` 方法用于将该计时周期添加到作为参数传递的指定时态对象中。

## 语法

```java
Temporal addTo(Temporal temporalObject)
```

## 参数

该方法接受一个参数 `temporalObject`，即该时间周期内需要调整的量。它不应为 `null`。

## 返回值

该方法返回一个相同类型的对象，并对其进行时间对象调整。

## 异常

此方法抛出以下异常：

*   `DateTimeException`：如果无法添加该周期。
*   `ArithmeticException`：如果发生数值溢出。

以下示例说明了 `ChronoPeriod.addTo()` 方法：

### 程序 1

```java
// Java code to show the function addTo()
// to add the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        // Adjust the time
        // using addTo() method
        System.out.println(
            p1.addTo(currentTime));
    }
}
```

**输出：**

```java
2024-05-27T14:23:35.242
```

### 程序 2

```java
// Java code to show the function addTo()
// to add the two given periods

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year1 = 2;
        int months1 = 7;
        int days1 = 8;
        ChronoPeriod p1 = Period.of(year1, months1, days1);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        // Adjust the time
        // using addTo() method
        System.out.println(
            p1.addTo(currentTime));
    }
}
```

**输出：**

```java
2022-01-25T14:23:50.411
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#addTo-java.time.temporal.Temporal-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#addTo-java.time.temporal.Temporal-)