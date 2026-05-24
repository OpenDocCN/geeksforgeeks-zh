# Java 中的 JapaneseChronology dateEpochDay() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-dateepochday-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-dateepochday-method-in-java-with-example/)

`Java.time.chrono.JapaneseChronology` 类的 `dateEpochDay()` 方法用于根据日本日历系统从大纪元日获取日本日期。

## 语法

```java
public JapaneseDate dateEpochDay(long epochDay)
```

## 参数

该方法以 `long` 类型的 `epochDay` 为参数。

## 返回值

该方法从另一个 `TemporalAccessor` 对象返回根据日本日历系统的本地日期。

## 异常

如果该纪元日无法创建日本日期，此方法抛出 `DateTimeException`。

以下是举例说明 `dateEpochDay()` 方法：

### 示例 1

```java
// Java program to demonstrate
// dateEpochDay() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("current JapaneseDate is: "
                               + hidate);

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nJapaneseDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
current JapaneseDate is: Japanese Reiwa 3-06-22

JapaneseDate(according to ephochday) is: Japanese Reiwa 16-03-22
```

### 示例 2

```java
// Java program to demonstrate
// dateEpochDay() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("current JapaneseDate is: "
                               + hidate);

            // getting JapaneseDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(-999999999);

            // display the result
            System.out.println("\nJapaneseDate(accoding "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出**

```java
current JapaneseDate is: Japanese Heisei 32-04-13
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: JapaneseDate before Meiji 6 is not supported
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateEpochDay-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateEpochDay-long-)