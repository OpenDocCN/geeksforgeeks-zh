# Java中的ChronoPeriod.getChronology()方法示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-getchronology-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-getchronology-method-in-java-with-examples/)

使用Java中`ChronoPeriod`接口的`getChronology()`方法获取此周期的年表，即ISO日历系统。

## 语法

```java
ChronoPeriod getChronology()
```

## 参数
该方法不接受任何参数。

## 返回值
此方法返回此周期的年表。

下面的程序说明了上述方法：

### 程序1

```java
// Java code to show the getChronology() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to negate given periods
    static void printChronology(ChronoPeriod p1)
    {

System.out.println(p1.getChronology());
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        ChronoPeriod p1 = Period.of(year, months, days);

printChronology(p1);
    }
}
```

### 输出

```java
ISO
```

### 程序2

```java
// Java code to show the getChronology() function

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodClass {

// Function to negate given periods
    static void printChronology(ChronoPeriod p1)
    {

System.out.println(p1.getChronology());
    }

// Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = -4;
        int months = -11;
        int days = -10;
        ChronoPeriod p1 = Period.of(year, months, days);

printChronology(p1);
    }
}
```

### 输出

```java
ISO
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#getChronology--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#getChronology--)