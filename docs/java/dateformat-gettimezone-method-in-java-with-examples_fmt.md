# Java 中的 DateFormat getTimeZone()方法，带示例

> 原文: [`https://www.geeksforgeeks.org/dateformat-gettimezone-method-in-java-with-examples/`](https://www.geeksforgeeks.org/dateformat-gettimezone-method-in-java-with-examples/)

`DateFormat`类中的`getTimeZone()`方法用于返回该日期格式日历的当前时区。

## 语法:
```java
public TimeZone getTimeZone()
```

## 参数:
该方法不取任何参数。

## 返回值:
该方法返回与日期格式的日历相关联的时区。

以下程序说明了`DateFormat`类的`getTimeZone()`方法的工作:

## 示例 1:
```java
// Java code to illustrate
// getTimeZone() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();

        // Converting the dateformat to string
        String str = DFormat.format(new Date());

        // Getting the available timezones
        System.out.println(DFormat
                               .getTimeZone()
                               .getDisplayName());
    }
}
```

## Output:
```java
Coordinated Universal Time
```

## 参考:
[`https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#getTimeZone()`](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#getTimeZone())