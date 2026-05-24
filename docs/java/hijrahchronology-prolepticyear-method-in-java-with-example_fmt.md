# Java 中的 HijrahChronology prolepticYear() 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-prolepticyear-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-prolepticyear-method-in-java-with-example/)

## 描述

`java.time.chrono.HijrahChronology` 类的 `prolepticYear()` 方法用于检索在特定 Hijrah 时代下，Hijrah 历法系统中的 proleptic 年份。

## 语法

```java
public int prolepticYear(Era era,
                         int yearOfEra)
```

## 参数

该方法接受以下参数：

*   `era`：即 Hijrah 时代的对象。
*   `yearOfEra`：特定 Hijrah 时代的年份。

## 返回值

该方法返回特定 Hijrah 时代在 Hijrah 历法系统中的 **proleptic 年**。

## 示例

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(HijrahEra.AH, 1444);

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

**输出：**

```java
proleptic Year is: 1444
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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(HijrahEra.AH, 1200);

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

**输出：**

```java
proleptic Year is: 1200
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#prolepticYear-java.time.chrono.Era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#prolepticYear-java.time.chrono.Era-int-)