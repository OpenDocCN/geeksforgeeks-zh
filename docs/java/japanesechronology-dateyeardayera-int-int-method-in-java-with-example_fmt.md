# JapaneseChronology.dateYearDay(Era, int, int) 方法

> 原文：[https://www.geeksforgeeks.org/japanesechronology-dateyeardayera-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-dateyeardayera-int-int-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `dateYearDay()` 方法用于根据特定时代的日本日历检索日本日期。

## 语法

```java
public JapaneseDate dateYearDay(
  Era era, int yearOfEra, int dayOfYear)
```

## 参数

该方法以下列参数为参数：

*   `era`：类型为 `Era` 的对象。
*   `yearOfEra`：表示日本日期年字段的整数年。
*   `dayOfYear`：表示日本日期的日字段的整数日。

## 返回值

此方法根据特定年份和日期的日本日历返回 `JapaneseDate`。

## 异常

该方法抛出 `DateTimeException` —— 如果给定的数据无法形成日期。

## 示例

以下是举例说明 `dateYearDay()` 方法的例子：

### 示例 1

```java
// Java program to demonstrate
// dateYearDay() method

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

            // getting JapaneseDate for the
            // given date and year field
            // by using dateYearDay() method
            JapaneseDate date
                = crono.dateYearDay(
                    JapaneseEra.HEISEI,
                    2018,
                    24);

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
JapaneseDate is: Japanese Heisei 2018-01-24
```

### 示例 2

```java
// Java program to demonstrate
// dateYearDay() method

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

            // getting JapaneseDate for the
            // given date and year field
            // by using dateYearDay() method
            JapaneseDate date
                = crono.dateYearDay(
                    JapaneseEra.MEIJI,
                    2018,
                    24);

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
passed parameter can not form a date
Exception thrown:
 java.time.DateTimeException:
 Invalid parameters
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateYearDay-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#dateYearDay-int-int-)