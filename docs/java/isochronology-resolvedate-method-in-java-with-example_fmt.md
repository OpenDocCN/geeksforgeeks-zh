# Java 中的 IsoChronology.resolveDate() 方法示例

> 原文：[https://www.geeksforgeeks.org/isochronology-resolvedate-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-resolvedate-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `resolveDate()` 方法用于根据 ISO 日历，通过在特定解析器样式的帮助下解析与 `Map` 中特定 `Long` 值相关联的 `ChronoField` 来检索 `LocalDate`。

## 语法

```java
public LocalDate resolveDate(
       Map<TemporalField,Long> fieldValues,
       ResolverStyle resolverStyle)
```

## 参数

该方法将以下参数作为参数：

*   `fieldValues`：这将包含时间字段。
*   `resolverStyle`：这将解析时间字段并提供日期。

## 返回值

该方法通过解析 `Map` 中与特定 `Long` 值相关联的 `ChronoField`，借助特定的 `ResolverStyle`，根据 ISO 日历返回 `LocalDate`。

以下示例说明了 `resolveDate()` 方法：

## 示例 1

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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.EPOCH_DAY,
                    30l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("LocalDate is : "
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

### 输出

```java
LocalDate is : 1970-01-31
```

## 示例 2

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
            // LocalDate Object
            LocalDate hidate
                = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
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
            System.out.println("LocalDate is : "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

### 输出

```java
LocalDate is : null
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)