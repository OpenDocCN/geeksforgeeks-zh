# Java 中的 MinguoChronology 的 getCalendarType() 方法示例

> 原文：[https://www.geeksforgeeks.org/minguochronology-getcalendartype-method-in-java-with-example/](https://www.geeksforgeeks.org/minguochronology-getcalendartype-method-in-java-with-example/)

`java.time.chrono.MinguoChronology` 类的 `getCalendarType()` 方法用于检索该 Minguo 年表系统下的日历类型。

## 语法

```java
public String getCalendarType()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回此 Minguo 年表系统下的日历类型字符串。

以下是举例说明 `getCalendarType()` 方法：

### 示例 1

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
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now();

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
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
Type of Calendar : roc
```

### 示例 2

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
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now(Clock.systemDefaultZone());

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
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
Type of Calendar : roc
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#getCalendarType--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#getCalendarType--)