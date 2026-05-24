# Java 中的 HijrahDate minus(long, TemporalUnit) 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahdate-minuslong-temporalunit-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-minuslong-temporalunit-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `minus()` 方法用于在从当前 Hijrah 日期中减去一定数量的时态单位后获取新的 Hijrah 日期。

**语法：**

```java
public HijrahDate minus(long amountToSubtract,
                        TemporalUnit unit)
```

**参数：** 该方法以下列参数为参数：

*   `amountToSubtract`：要从当前 Hijrah 日期中减去的时间单位值。
*   `unit`：一个时间单位或小时单位的对象。

**返回值：** 此方法在当前 Hijrah 日期减去一个时间单位后，返回 `HijrahDate`。

以下是举例说明 `minus()` 方法的例子：

**例 1：**

## Java

```java
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // Display the result
            System.out.println("old hijrah date: "
                               + hidate);

            // Subtracting hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.minus(
                    22, ChronoUnit.DAYS);

            // Display the result
            System.out.println("new hijrah date: "
                               + newdate);
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
old hijrah date: Hijrah-umalqura AH 1441-06-25
new hijrah date: Hijrah-umalqura AH 1441-06-03
```

**例 2：**

## Java

```java
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Dreating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // Display the result
            System.out.println("old hijrah date: "
                               + hidate);

            // Subtracting hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.minus(
                    4, ChronoUnit.DECADES);

            // Display the result
            System.out.println("new hijrah date: "
                               + newdate);
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
old hijrah date: Hijrah-umalqura AH 1441-06-25
new hijrah date: Hijrah-umalqura AH 1401-06-25
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#minus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#minus-long-java.time.temporal.TemporalUnit-)