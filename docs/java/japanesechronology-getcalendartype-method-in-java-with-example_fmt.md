# Java 中的 JapaneseChronology.getCalendarType() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-getcalendartype-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-getcalendartype-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `getCalendarType()` 方法用于检索这个日语年表系统下的日历类型。

**语法：**
```java
public String getCalendarType()
```

**参数：** 此方法不接受任何参数。
**返回值：** 这个方法返回在此日本时间系统下的日历类型。

以下是举例说明 `getCalendarType()` 方法：

## 示例 1

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
        // JapaneseDate Object
        JapaneseDate hidate
            = JapaneseDate.now();

        // getting JapaneseChronology
        // used in JapaneseDate
        JapaneseChronology crono
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

**输出：**
```java
Type of Calendar : japanese
```

## 示例 2

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
        // JapaneseDate Object
        JapaneseDate hidate
            = JapaneseDate.now(
                Clock.systemDefaultZone());

        // getting JapaneseChronology
        // used in JapaneseDate
        JapaneseChronology crono
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

**输出：**
```java
Type of Calendar : japanese
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#getCalendarType--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#getCalendarType--)