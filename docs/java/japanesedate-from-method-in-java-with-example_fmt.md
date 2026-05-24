# Java 中的 `JapaneseDate` `from()` 方法示例

> 原文：[https://www.geeksforgeks.org/japanesedate-from-method-in-java-with-example/](https://www.geeksforgeks.org/japanesedate-from-method-in-java-with-example/)

`java.time.chrono.JapaneseDate` 类的 `from()` 方法用于根据特定时间对象的日本日历系统获取日本日期。

### 语法
```java
public static JapaneseDate from(
       TemporalAccessor temporal)
```

### 参数
该方法取 `TemporalAccessor` 的对象，以此为基础形成日本日期。

### 返回值
该方法根据指定时态对象的日本历法系统返回 `JapaneseDate`。

以下是举例说明 `from()` 方法：

## 示例 1

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
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.from(zonedate);

            // Display the result
            System.out.println("JapaneseDate: "
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

**输出**
```java
JapaneseDate: Japanese Heisei 30-10-25
```

## 示例 2

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
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.from(localdate);

            // Display the result
            System.out.println("JapaneseDate: "
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

**输出**
```java
JapaneseDate: Japanese Heisei 30-12-30
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#from-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#from-java.time.temporal.TemporalAccessor-)