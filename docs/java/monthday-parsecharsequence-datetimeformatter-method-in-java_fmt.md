# Java 中的 MonthDay.parse(CharSequence, DateTimeFormatter) 方法

> 原文：[https://www.geeksforgeeks.org/monthday-parsecharsequence-datetimeformatter-method-in-java/](https://www.geeksforgeeks.org/monthday-parsecharsequence-datetimeformatter-method-in-java/)

Java 中的 `MonthDay` 类的 `parse(CharSequence text, DateTimeFormatter formatter)` 方法用于使用特定的格式化程序从文本字符串中获取 `MonthDay` 的实例。

## 语法

```java
public static MonthDay parse(
    CharSequence text, 
    DateTimeFormatter formatter)
```

## 参数

此方法接受两个参数：
*   `text`：要解析的文本。
*   `formatter`：要使用的格式化程序。

## 返回值

该方法返回解析后的 `MonthDay`。

## 异常

如果文本无法解析，该方法抛出 `DateTimeParseException`。

## 示例

下面的程序说明了 Java 中 `MonthDay` 的 `parse` 方法：

### 程序 1

```java
// Java program to demonstrate
// MonthDay.parse(CharSequence text,
// DateTimeFormatter formatter) method

import java.time.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // apply ofpattern() method
        // of DateTimeFormatter class
        DateTimeFormatter datetimeformatter
            = DateTimeFormatter.ofPattern("--MM-dd");

        // apply parse(CharSequence text,
        // DateTimeFormatter formatter) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09", datetimeformatter);

        // print monthday
        // in mm-dd format
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```java
MonthDay: --05-09
```

### 程序 2

```java
// Java program to demonstrate
// MonthDay.parse(CharSequence text,
// DateTimeFormatter formatter) method

import java.time.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // apply ofpattern() method
        // of DateTimeFormatter class
        DateTimeFormatter datetimeformatter
            = DateTimeFormatter.ofPattern("--dd-MM");

        // apply parse(CharSequence text,
        // DateTimeFormatter formatter) method
        // of MonthDay class
        MonthDay monthday = MonthDay.parse(
            "--05-09", datetimeformatter);

        // print monthday
        // in dd-mm format
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```java
MonthDay: --09-05
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))