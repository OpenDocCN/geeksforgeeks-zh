# Java 中的 JapaneseChronology.isLeapYear() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesechronology-isleapyear-method-in-java-with-example/](https://www.geeksforgeeks.org/japanesechronology-isleapyear-method-in-java-with-example/)

`java.time.chrono.JapaneseChronology` 类的 `isLeapYear()` 方法用于区分闰年和非闰年。如果是闰年，它将返回真，否则返回假。

## 语法

```java
public boolean isLeapYear(long prolepticYear)
```

## 参数

该方法以 `prolepticYear` 为参数，检查是否为闰年。

## 返回值

如果前一年是闰年，该方法返回 `boolean` 值为 `true`，否则为 `false`。

## 示例

以下是说明该方法的示例：

### 示例 1

```java
// Java program to demonstrate
// isLeapYear() method

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

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(1444);

        // display the result
        if (flag)
            System.out.println(
                "this is leap year");
        else
            System.out.println(
                "this is non leap year");
    }
}
```

**输出：**

```java
this is leap year
```

### 示例 2

```java
// Java program to demonstrate
// isLeapYear() method

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

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(2005);

        // display the result
        if (flag)
            System.out.println(
                "this is leap year");
        else
            System.out.println(
                "this is non leap year");
    }
}
```

**输出：**

```java
this is non leap year
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#isLeapYear-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#isLeapYear-long-)