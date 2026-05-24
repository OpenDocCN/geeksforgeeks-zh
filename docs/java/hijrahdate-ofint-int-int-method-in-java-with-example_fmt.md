# HijrahDate 的 of(int, int, int) 方法及示例

> 原文: [https://www.geeksforgeks.org/hijrahdate-ofint-int-int-method-in-java-with-example/](https://www.geeksforgeks.org/hijrahdate-ofint-int-int-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `of()` 方法用于根据伊斯兰回历系统，利用传递的公历年、月、日生成日期。

## 语法

```java
public static HijrahDate of(int year,
            int month, int dayOfMonth)
```

## 参数

该方法接受以下参数：
*   `year`：表示回历日期中年份字段的整数值。
*   `month`：表示 Hijrah 日期中的月字段的整数值。
*   `dayOfMonth`：是日的整数值，代表 Hijrah 日期中的日字段。

## 返回值

该方法根据伊斯兰回历系统，用经过的年、月、日返回一个 `HijrahDate`。

## 异常

如果传递的参数不能形成有效日期，该方法抛出 `DateTimeException`。

以下是 `of()` 方法的示例：

## 示例 1

```java
// Java program to demonstrate of() method

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
            // By using of() method
            HijrahDate hidate
                = HijrahDate.of(1444, 04, 24);

// Display the result
            System.out.println("HijrahDate: "
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

**输出：**

```java
HijrahDate: Hijrah-umalqura AH 1444-04-24
```

## 示例 2

```java
// Java program to demonstrate of() method

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
            // By using of() method
            HijrahDate hidate
                = HijrahDate.of(2014, 04, 24);

// Display the result
            System.out.println("HijrahDate: "
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

**输出：**

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException:
                  Invalid Hijrah date,
                  year: 2014, month: 4
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#of-int-int-int-)