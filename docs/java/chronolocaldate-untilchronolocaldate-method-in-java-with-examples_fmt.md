# Java 中的计时日期截止(计时日期)方法，示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldate-untilchronolocaldate-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-untilchronolocaldate-method-in-java-with-examples/)

`ChronoLocalDate`接口的`until()`方法，用于获取该本地日期和作为参数传递的另一个日期之间的差值，并根据计时周期对象返回差值。此操作按年、月、日执行，并以相同方式返回答案。起点是这个`ChronoLocalDate`，终点是作为参数传递的指定日期。当开始点在日期方面晚于结束点时，返回值为负。国际标准化组织日历对于这种方法非常重要，因为计算是使用国际标准化组织日历系统进行的。

## 语法

```java
public ChronoPeriod until(ChronoLocalDate endDateExclusive)
```

## 参数

此方法接受一个参数`endDateExclusive`，它是结束日期，Exclusive，它可以在任何年表中，它不应该为空。

## 返回值

此方法返回此日期和结束日期之间的期间。

以下程序说明了`until()`方法：

## 示例

```java
// Java program to demonstrate
// ChronoLocalDate.until() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDate objects
        ChronoLocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        ChronoLocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until the method of LocalDate class
        ChronoPeriod result
            = l2.until(l1);

        // print results
        System.out.println("Result in Period: "
                           + result);
    }
}
```

**Output:**

```java
Result in Period: P1M11D
```

## 示例

```java
// Java program to demonstrate
// ChronoLocalDate.until() method

import java.time.*;
import java.time.temporal.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {
        // create ChronoLocalDate objects
        ChronoLocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        ChronoLocalDate l2
            = LocalDate
                  .parse("2018-12-15");

        // apply until()
        ChronoPeriod result
            = l2.until(l1);

        // print results
        System.out.println("Result in Period: "
                           + result);
    }
}
```

**Output:**

```java
Result in Period: P-9D
```

## 参考资料

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#until-java.time.chrono.ChronoLocalDate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#until-java.time.chrono.ChronoLocalDate-)