# Java 中的 IsoChronology.dateYearDay(int, int) 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-dateyeardayint-int-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-dateyeardayint-int-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `dateYearDay()` 方法用于根据特定年份和日期的 Iso 日历检索 `LocalDate`。

**语法：**

```java
public LocalDate dateYearDay(int prolepticYear,
                             int dayOfYear)
```

**参数：** 该方法以下列参数为参数：
*   `prolepticYear`：是 `LocalDate` 年字段的整数优先年。
*   `dayOfYear`：是 `LocalDate` 的日字段的整数日。

**返回值：** 该方法根据特定年份和日期的 Iso 日历返回 `LocalDate`。

以下是举例说明 `dateYearDay()` 方法的例子：

## 例 1

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting LocalDate for the
            // given date and year field
            // by using dateYearDay() method
            LocalDate date = crono.dateYearDay(1440, 24);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
LocalDate is: 1440-01-24
```

## 例 2

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting LocalDate for the
            // given date and year field
            // by using dateYearDay() method
            LocalDate date = crono.dateYearDay(999999999, 32);

            // display the result
            System.out.println("LocalDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
LocalDate is: +999999999-02-01
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateYearDay-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateYearDay-int-int-)