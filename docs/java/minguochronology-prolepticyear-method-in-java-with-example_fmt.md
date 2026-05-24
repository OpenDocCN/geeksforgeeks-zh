# Java 中的 Minguo 年表 `prolepticYear()` 方法示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-prolepticyear-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-prolepticyear-method-in-java-with-example/)

`java.time.chrono.MinguoChronology` 类的 `prolepticYear()` 方法用于检索出现在特定民国时代的民国系统中的 proleptic year。

## 语法

```java
public int prolepticYear(Era era,
                         int yearOfEra)
```

## 参数

该方法以下列参数为参数。

*   `era`：即民国时代的对象。
*   `yearOfEra`：是民国纪年的年份。

## 返回值

此方法返回特定民国时代民国系统中出现的 proleptic year。

以下是说明 `prolepticYear()` 方法的示例：

## 示例 1

```java
// Java program to demonstrate
// prolepticYear() method

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

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    MinguoEra.ROC,
                    1444);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
proleptic Year is: 1444
```

## 示例 2

```java
// Java program to demonstrate
// prolepticYear() method

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

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    MinguoEra.BEFORE_ROC,
                    1444);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出：**

```java
proleptic Year is: -1443
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#prolepticYear-java.time.chrono.Era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#prolepticYear-java.time.chrono.Era-int-)