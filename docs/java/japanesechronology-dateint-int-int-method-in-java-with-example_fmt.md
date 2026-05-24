# Java 中的 JapaneseChronology date(int, int, int) 方法示例

> 原文: [https://www.geeksforgeeks.org/japanesechronology-dateint-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-dateint-int-int-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `date()` 方法用于根据日本日历系统获取给定年、月和日的 `LocalDate`。

**语法:**

```java
public JapaneseDate date(int prolepticYear,
                         int month,
                         int dayOfMonth)
```

**参数:** 该方法接受以下参数：
*   `prolepticYear`: 日本年份字段的整数普理年。
*   `month`: 日语月字段的整数月。
*   `dayOfMonth`: 日本人日字段的整数日。

**返回值:** 该方法根据日本日历系统返回给定年、月、日的 `JapaneseDate`。

**异常:** 如果给定的日、月、年字段无法形成结构化日期，该方法抛出 `DateTimeException`。

以下举例说明 `date()` 方法：

## 示例

```java
// Java program to demonstrate
// date() method

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
            JapaneseDate lodate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in JapaneseDate
            JapaneseChronology crono
                = lodate.getChronology();

            // getting JapaneseDate for the
            // given date, month and year field
            // by using date() method
            JapaneseDate date
                = crono.date(2018, 05, 24);

            // display the result
            System.out.println(
                "JapaneseDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
JapaneseDate is: Japanese Heisei 30-05-24
```