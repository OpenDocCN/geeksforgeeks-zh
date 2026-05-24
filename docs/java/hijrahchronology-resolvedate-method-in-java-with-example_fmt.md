# Java 中的 HijrahChronology resolveDate() 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahchronology-resolvedate-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-resolvedate-method-in-java-with-example/)

`java.time.chrono.HijrahChronology` 类的 `resolveDate()` 方法用于根据伊斯兰回历检索本地日期，方法是借助特定的 `ResolverStyle` 解析地图中与特定长值相关联的时间字段。

## 语法

```java
public HijrahDate resolveDate(Map fieldValues,
                              ResolverStyle resolverStyle)
```

## 参数

该方法将以下参数作为参数：

*   `fieldValues`： 包含时间字段。
*   `resolverStyle`： 解析时间字段并提供日期。

## 返回值

该方法通过在特定解析器样式的帮助下解析地图中与特定长值相关联的 Chrono 字段，根据伊斯兰回历返回 `LocalDate`。

## 示例

以下示例说明了 `resolveDate()` 方法：

### 示例 1

```java
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)ChronoField
                        .EPOCH_DAY,
                    1000l);
            map.put((TemporalField)ChronoField
                        .HOUR_OF_AMPM,
                    2000l);
            map.put((TemporalField)ChronoField
                        .HOUR_OF_DAY,
                    3000l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.SMART);

            // display the result
            System.out.println("HijrahDate is : "
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
HijrahDate is : Hijrah-umalqura AH 1392-08-19
```

### 示例 2

```java
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // getting HijrahChronology
            // used in HijrahDate
            HijrahChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.HOUR_OF_AMPM,
                    2000l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("HijrahDate is : "
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
HijrahDate is : null
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)