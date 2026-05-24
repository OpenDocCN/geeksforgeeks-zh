# Java 中的 Minguo 年表 `dateNow(Clock)` 方法，示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-datenowclock-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-datenowclock-method-in-java-with-example/)

`java.time.chrono.MinguoChronology` 类的 `dateNow()` 方法用于从指定的时钟对象中根据 Minguo 日历系统获取当前的 Minguo 日期。

## 语法

```java
public MinguoDate dateNow(Clock clock)
```

## 参数

该方法以 `Clock` 的对象为参数，用于从指定的时钟对象中获取根据民国历法系统的当前民国日期。

## 返回值

该方法从指定的时钟对象返回根据民国日历系统的民国日期。

以下是举例说明 `dateNow()` 方法的例子：

### 例 1

```java
// Java program to demonstrate
// MinguoNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // clock object
            Clock clock = Clock.systemUTC();

            // getting MinguoDate for the
            // given clock object
            // by using dateNow() method
            MinguoDate date
                = crono.dateNow(clock);

            // display the result
            System.out.println(
                "MinguoDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
MinguoDate is: Minguo ROC 109-04-15
```

### 例 2

```java
// Java program to demonstrate
// MinguoNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing
            // clock object
            Clock clock = Clock.systemUTC();

            // setting clock
            clock = Clock.tick(
                clock,
                Duration.ofDays(100));

            // getting MinguoDate for the
            // given clock object
            // by using dateNow() method
            MinguoDate date
                = crono.dateNow(clock);

            // display the result
            System.out.println(
                "MinguoDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
MinguoDate is: Minguo ROC 109-02-08
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateNow-java.time.Clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateNow-java.time.Clock-)