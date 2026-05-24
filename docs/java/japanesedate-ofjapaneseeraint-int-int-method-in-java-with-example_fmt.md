# JapaneseDate.of(JapaneseEra, int, int, int) 方法示例

> 原文: [https://www.geeksforgeeks.org/japanesedate-ofjapaneseeraint-int-int-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesedate-ofjapaneseeraint-int-int-method-in-java-with-example/)

`JapaneseDate` 类的 `of()` 方法用于根据日本日历系统，使用给定的 era、年、月、日生成日期。

## 语法

```java
public static JapaneseDate of(JapaneseEra era,
                              int yearOfEra,
                              int month,
                              int dayOfMonth)
```

## 参数

该方法接受以下参数：

*   `era`: 日本时代的对象，代表日本日期中的时代字段。
*   `yearOfEra`: 表示日本日期中年份字段的整数值。
*   `month`: 表示日本日期中月份字段的整数值。
*   `dayOfMonth`: 表示日本日期中日字段的整数值。

## 返回值

该方法根据日本历法系统，使用给定的 era、年、月、日，返回一个 `JapaneseDate`。

## 异常

如果传递的参数不能形成有效日期，该方法抛出 `DateTimeException`。

## 示例

### 示例 1

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
            // JapaneseDate Object
            // By using of() method
            JapaneseDate hidate
                = JapaneseDate.of(
                    JapaneseEra.HEISEI,
                    2008, 04, 24);

            // Display the result
            System.out.println("JapaneseDate: "
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

**输出:**

```java
JapaneseDate: Japanese Heisei 2008-04-24
```

### 示例 2

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
            // JapaneseDate Object
            // By using of() method
            JapaneseDate hidate
                = JapaneseDate.of(
                    JapaneseEra.TAISHO,
                    2008, 04, 24);

            // Display the result
            System.out.println("JapaneseDate: "
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

**输出:**

```java
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: year, month, and day not valid for Era
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#of-java.time.chrono.JapaneseEra-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#of-java.time.chrono.JapaneseEra-int-int-int-)