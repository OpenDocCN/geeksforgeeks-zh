# Java 中的 Minguo 年表 resolveDate()方法，示例

> 原文: [https://www.geeksforgeeks.org/minguochronology-resolvedate-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-resolvedate-method-in-java-with-example/)

`java.time.chrono.MinguoChronology`类的`resolveDate()`方法用于通过在特定的解析器样式的帮助下解析与地图中特定长值相关联的时间字段来根据民国日历检索民国日期。

## 语法:
```java
public MinguoDate resolveDate(
       Map fieldValues,
       ResolverStyle resolverStyle)
```

## 参数:
该方法将以下参数作为参数:

*   `fieldValues`: This will contain the timing field.
*   `resolverStyle`: This will parse the time field and provide the date.

## 返回值:
该方法通过解析地图中特定长值关联的 Chrono 字段，借助特定解析器样式，根据民国日历返回本地日期。

以下示例说明了`resolveDate()`方法:

## 例 1:
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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting  MinguoChronology
            // used in  MinguoDate
            MinguoChronology crono
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
            System.out.println("MinguoDate is : "
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

## 输出:
```java
MinguoDate is : Minguo ROC 59-01-31
```

## 例 2:
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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now();

            // getting  MinguoChronology
            // used in  MinguoDate
            MinguoChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.HOUR_OF_AMPM,
                    30l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("MinguoDate is : "
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

## 输出:
```java
MinguoDate is : null
```

## 参考:
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)