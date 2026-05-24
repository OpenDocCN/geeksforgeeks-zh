# Java 中的 JapaneseChronology.dateNow(Clock) 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-datenowclock-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-datenowclock-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `dateNow(Clock clock)` 方法用于从指定的时钟对象中获取根据日本日历系统的当前日本日期。

## 语法

```java
public JapaneseDate dateNow(Clock clock)
```

## 参数

该方法以 `Clock` 的对象为参数，用于从指定的时钟对象中获取根据日本日历系统的当前日本日期。

## 返回值

此方法从指定的时钟对象返回根据日本日历系统的日本日期。

以下是举例说明 `dateNow(Clock clock)` 方法的例子：

## 示例 1

```java
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // creating and initializing
            // clock object
            Clock clock = Clock.systemUTC();

            // getting JapaneseDate for the
            // given clock object
            // by using dateNow() method
            JapaneseDate date
                = crono.dateNow(clock);

            // display the result
            System.out.println(
                "JapaneseDate is: "
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
JapaneseDate is: Japanese Heisei 32-03-11
```

## 示例 2

```java
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // creating and initializing
            // clock object
            Clock clock
                = Clock.systemUTC();

            // setting clock
            clock = Clock.tick(
                clock,
                Duration.ofDays(100));

            // getting JapaneseDate for the
            // given clock object
            // by using dateNow() method
            JapaneseDate date
                = crono.dateNow(clock);

            // display the result
            System.out.println(
                "JapaneseDate is: "
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
JapaneseDate is: Japanese Heisei 32-02-08
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateNow-java.time.Clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateNow-java.time.Clock-)