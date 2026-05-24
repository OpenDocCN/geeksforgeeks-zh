# Java 中的 IsoChronology prolepticYear() 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-prolepticyear-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-prolepticyear-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `prolepticYear()` 方法用于检索特定回历时代的 Iso 系统中存在的 proleptic year。

## 语法

```java
public int prolepticYear(Era era,
                         int yearOfEra)
```

## 参数

该方法将以下参数作为参数。

*   `Era`：是 Iso 时代的对象。
*   `yearOfEra`：这是特定 Iso 时代的年份。

## 返回值

该方法返回特定 Iso 时代的 Iso 系统中存在的年份。

以下是说明 `prolepticYear()` 方法的示例：

### 例 1

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(IsoEra.CE, 2020);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

### 输出

```java
proleptic Year is: 2020
```

### 例 2

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology used in LocalDate
            IsoChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(IsoEra.BCE, 1980);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

### 输出

```java
proleptic Year is: -1979
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#prolepticYear-java.time.chrono.Era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#prolepticYear-java.time.chrono.Era-int-)