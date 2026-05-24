# Java 中的 `ChronoPeriod.normalized()` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-negated-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-negated-method-in-java-with-examples/)

Java 中 `ChronoPeriod` 接口的 `normalized()` 方法，用于归一化年、月后返回计时周期的新实例。

## 语法

```java
ChronoPeriod normalized()
```

## 参数
该功能不接受任何参数。

## 返回值
该函数在对期间的年和月进行归一化后，返回一个 `ChronoPeriod` 的新实例。

## 异常
它抛出一个 `ArithmeticException`。如果发生数字溢出，将捕获此异常。

下面的程序说明了上面的方法：

## 程序 1

```java
// Java code to show the function to normalize
// months and years of the period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to normalize given periods
    static void toNormalize(ChronoPeriod p1)
    {

System.out.println(p1.normalized());
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 15;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

toNormalize(p1);
    }
}
```

**输出：**

```java
P5Y3M10D
```

## 程序 2
这不会使天数正常化。

```java
// Java code to show the function to normalize
// months and years of the period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to normalize given periods
    static void toNormalize(ChronoPeriod p1)
    {

System.out.println(p1.normalized());
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 10;
        int months = 25;
        int days = 366;
        ChronoPeriod p1 = Period.of(year, months, days);

toNormalize(p1);
    }
}
```

**输出：**

```java
P12Y1M366D
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#normalized--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#normalized--)