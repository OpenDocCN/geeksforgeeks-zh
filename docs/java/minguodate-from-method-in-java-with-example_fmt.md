# Java 中的 MinguoDate from()方法示例

> 原文：[https://www.geeksforgeeks.org/minguodate-from-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-from-method-in-java-with-example/)

`Java.time.chrono.MinguoDate` 类的 `from()` 方法用于根据特定时间对象的民国日历系统获取民国日期。

## 语法

```java
public static MinguoDate from(TemporalAccessor temporal)
```

## 参数

该方法取任意时态取值器的对象，以此为基础形成民国日期。

## 返回值

该方法根据指定时态对象的民国日历系统返回民国日期。

以下是举例说明 `from()` 方法：

### 例 1

```java
// Java program to demonstrate from() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

// creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime
                      .parse(
                          "2018-10-25T23:12:31."
                          + "123+02:00[Europe/Paris]");

// Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.from(zonedate);

// Display the result
            System.out.println("MinguoDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出：**

```java
MinguoDate: Minguo ROC 107-10-25
```

### 例 2

```java
// Java program to demonstrate from() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

// creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

// Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.from(localdate);

// Display the result
            System.out.println("MinguoDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出：**

```java
MinguoDate: Minguo ROC 107-12-30
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#from-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#from-java.time.temporal.TemporalAccessor-)