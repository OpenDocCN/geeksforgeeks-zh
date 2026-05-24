# Java 中的 ChronoPeriod get()方法，示例

> 原文：[https://www.geeksforgeeks.org/chronoperiod-get-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronoperiod-get-method-in-java-with-examples/)

Java 中`ChronoPeriod`接口的`get()`方法用于从该计时周期中获取参数中给出的请求单位（年、月或日）的值。

## 语法：

```java
long get(TemporalUnit unit)
```

## 参数：
该方法接受一个类型为`TemporalUnit`的单参数`unit`，该单位是获得所需单位的单位。

## 返回值：
该函数返回请求单位的长值。

## 异常：

*   `DateTimeException` – 如果参数中的单位不受支持，此方法将抛出日期时间异常。
*   `UnsupportedTemporalTypeException` – 如果参数中的单位不受支持，此方法将抛出不受支持的时间类型异常。

下面的程序说明了上述方法：

## 程序 1：

```java
// Java code to show the function get()
// which gives the requested unit

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.DAYS));
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 8;
        int months = 5;
        int days = 25;

        getUnit(year, months, days);
    }
}
```

## 输出：

```java

```

## 程序二：

```java
// Java code to show the function get()
// which gives the requested unit

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoUnit;

public class ChronoPeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        ChronoPeriod period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.YEARS));
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 11;
        int months = 3;
        int days = 21;

        getUnit(year, months, days);
    }
}
```

## 输出：

```java

```

## 参考：
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#get-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoPeriod.html#get-java.time.temporal.TemporalUnit-)