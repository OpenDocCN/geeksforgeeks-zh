# Java 中的 HijrahChronology getCalendarType()方法示例

> 原文: [https://www.geeksforgeeks.org/hijrahchronology-getcalendartype-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-getcalendartype-method-in-java-with-example/)

`Java.time.chrono.HijrahChronology`类的`getCalendarType()`方法用于检索该 Hijrah 年表系统下的日历类型。

**语法:**
```java
public String getCalendarType()
```

**参数:** 此方法不接受任何参数。
**返回值:** 该方法返回该 Hijrah 时间系统下的日历类型字符串。

以下是举例说明`getCalendarType()`方法：

### 代码示例

```java
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // HijrahDate Object
        HijrahDate hidate
            = HijrahDate.now();

        // getting HijrahChronology
        // used in HijrahDate
        HijrahChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**输出**
```java
Type of Calendar : islamic-umalqura
```