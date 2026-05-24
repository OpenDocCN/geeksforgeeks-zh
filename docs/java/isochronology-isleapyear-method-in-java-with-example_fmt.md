# Java 中的 IsoChronology isLeapYear() 方法示例

> 原文: [https://www.geeksforgeeks.org/isochronology-isleapyear-method-in-java-with-example/](https://www.geeksforgeeks.org/isochronology-isleapyear-method-in-java-with-example/)

`java.time.chrono.IsoChronology` 类的 `isLeapYear()` 方法用于区分闰年和非闰年。如果是闰年，它将返回真或假。

## 语法

```java
public boolean isLeapYear(long prolepticYear)
```

## 参数

该方法以 `prolepticYear` 为参数，检查是否为闰年。

## 返回值

如果前一年是闰年，该方法返回布尔值 `true`，否则返回 `false`。

## 示例

以下是说明该方法的示例：

### 例 1

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
        // creating and initializing LocalDate Object
        LocalDate hidate = LocalDate.now();

        // getting IsoChronology used in LocalDate
        IsoChronology crono = hidate.getChronology();

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(1444);

        // display the result
        if (flag)
            System.out.println("this is leap year");
        else
            System.out.println("this is non leap year");
    }
}
```

**输出:**

```java
this is leap year
```

### 例 2

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
        // creating and initializing LocalDate Object
        LocalDate hidate = LocalDate.now();

        // getting IsoChronology used in LocalDate
        IsoChronology crono = hidate.getChronology();

        // getting id of this Chronology
        // by using isLeapYear() method
        boolean flag = crono.isLeapYear(2005);

        // display the result
        if (flag)
            System.out.println("this is leap year");
        else
            System.out.println("this is non leap year");
    }
}
```

**输出:**

```java
this is non leap year
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#isLeapYear-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#isLeapYear-long-)