# Java 中的 IsoChronology dateEpochDay() 方法示例

> 原文: [https://www.geeksforgeeks.org/isochronology-dateepochday-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-dateepochday-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `dateEpochDay()` 方法用于从大纪元日获取符合 ISO 系统的本地日期。

**语法：**
```java
public IsoDate dateEpochDay(long epochDay)
```

**参数：** 该方法以 `long` 类型的 `epochDay` 为参数。
**返回值：** 该方法根据 Hijrah 日历系统，从另一个临时处理器对象返回 `IsoDate`。

以下是举例说明 `dateEpochDay()` 方法：

## 示例 1

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
            // creating and initializing LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // display the result
            System.out.println("current LocalDate is: "
                               + hidate);

            // getting LocalDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nLocalDate(according "
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
current LocalDate is: 2021-06-25

LocalDate(according to ephochday) is: 2034-03-22
```

## 示例 2

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
            // creating and initializing  LocalDate Object
            LocalDate hidate = LocalDate.of(00000, 01, 01);

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // display the result
            System.out.println("current LocalDate is: "
                               + hidate);

            // getting LocalDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(-999999999);

            // display the result
            System.out.println("\nLocalDate(according "
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
current LocalDate is: 0000-01-01

LocalDate(according to ephochday) is: -2735938-12-30
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateEpochDay-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#dateEpochDay-long-)