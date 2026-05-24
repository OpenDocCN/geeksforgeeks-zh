# Java 中的 IsoChronology.range() 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-range-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-range-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `range()` 方法用于从类型为 `ChronoField` 的指定字段中获取值的范围。

## 语法

```java
public ValueRange range(ChronoField field)
```

## 参数

该方法以 `ChronoField` 类型的字段为参数。

## 返回值

该方法从指定的类型为 `ChronoField` 的字段中返回值的范围。

以下是说明 `range()` 方法的示例：

## 例 1

```java
// Java program to demonstrate
// range() method

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(
                    ChronoField.ERA);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
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

## 输出

```java
Equivalent Range : 0 - 1
```

## 例 2

```java
// Java program to demonstrate
// range() method

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = crono.range(
                    ChronoField.YEAR);

            // display the result
            System.out.println(
                "Equivalent Range : "
                + range);
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

## 输出

```java
Equivalent Range : -999999999 - 999999999
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#range-java.time.temporal.ChronoField-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#range-java.time.temporal.ChronoField-)