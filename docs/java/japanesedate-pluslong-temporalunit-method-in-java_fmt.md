# JapaneseDate plus(long, TemporalUnit)方法在Java中的使用

> 原文：[https://www.geeksforgeeks.org/japanesedate-pluslong-temporalunit-method-in-java/](https://www.geeksforgeeks.org/japanesedate-pluslong-temporalunit-method-in-java/)

`java.time.chrono.JapaneseDate`类的`plus()`方法用于在当前日语日期的基础上增加一定数量的时态访问器单元，得到日语日期。

**语法：**

```java
public JapaneseDate plus(long amountToAdd,
                         TemporalUnit unit)
```

**参数：** 该方法以以下参数为参数：

*   `amountToAdd`：是时间单位的数量，将与当前日本日期相加。
*   `unit`：是时间单位或时辰单位的对象。

**返回值：** 该方法将当前日语日期加上一定量的时态取值单位后，返回`JapaneseDate`。

下面举例说明`plus()`的方法：

## 示例1

```java
// Java program to demonstrate
// plus() method

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
            JapaneseDate hidate
                = JapaneseDate.of(
                    4000, 06, 23);

            // Display the result
            System.out.println(
                "Old Japanese date: "
                + hidate);

            // Adding some amount in Japanese date
            // by using plus() method
            JapaneseDate newdate
                = hidate.plus(
                    22,
                    ChronoUnit.DAYS);

            // Display the result
            System.out.println(
                "New Japanese date: "
                + newdate);
        }
        catch (DateTimeException e) {

            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出：**

```java
Old Japanese date: Japanese Heisei 2012-06-23
New Japanese date: Japanese Heisei 2012-07-15
```

## 示例2

```java
// Java program to demonstrate
// plus() method

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
            JapaneseDate hidate
                = JapaneseDate.of(
                    4000, 06, 23);

            // Display the result
            System.out.println(
                "Old Japanese date: "
                + hidate);

            // Adding some amount in Japanese date
            // by using minus() method
            JapaneseDate newdate
                = hidate.plus(
                    6,
                    ChronoUnit.YEARS);

            // Display the result
            System.out.println(
                "New Japanese date: "
                + newdate);
        }
        catch (DateTimeException e) {

            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出：**

```java
Old Japanese date: Japanese Heisei 2012-06-23
New Japanese date: Japanese Heisei 2018-06-23
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#plus-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#plus-long-java.time.temporal.TemporalUnit-)