# Java 中的 ChronoPeriod.multipliedBy() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-multipliedby-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-multipliedby-method-in-java-with-examples/)

Java 中 `ChronoPeriod` 接口的 `multipliedBy()` 方法，用于在给定周期的 YEAR，MONTH，DAY 周期的每个元素乘以‘X’(标量)后，返回计时周期的新实例。该功能仅适用于所有三个年份、月份和日期。

## 语法

```java
public ChronoPeriod multipliedBy(int toMultiply)
```

## 参数

此方法接受单个参数 `toMultiply`，这是要乘以周期的标量数。

## 返回值

此方法在将周期的每个元素乘以给定的倍数输入后，返回一个新的 `ChronoPeriod` 实例。

## 异常

它抛出一个 `ArithmeticException`。如果发生数字溢出，将捕获此异常。

以下是上述方法的实现：

## 程序一

```java
// Java code to show the function multipliedBy()
// to multiply the given number to given period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to multiply a constant to given periods
    static void multiply(ChronoPeriod p1, int toMultiply)
    {
        System.out.println(p1.multipliedBy(toMultiply));
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

        int toMultiply = 2;

        multiply(p1, toMultiply);
    }
}
```

输出：

```java
P8Y22M20D
```

## 程序二

```java
// Java code to show the function multipliedBy()
// to multiply the given number to given period

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to multiply a constant to given periods
    static void multiply(ChronoPeriod p1, int toMultiply)
    {
        System.out.println(p1.multipliedBy(toMultiply));
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining first period
        int year = -4;
        int months = -11;
        int days = -10;
        ChronoPeriod p1 = Period.of(year, months, days);

        int toMultiply = 2;

        multiply(p1, toMultiply);
    }
}
```

输出：

```java
P-8Y-22M-20D
```

参考：[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#multipliedBy-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#multipliedBy-int-)