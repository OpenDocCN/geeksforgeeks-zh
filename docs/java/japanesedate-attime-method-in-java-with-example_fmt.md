# Java 中的 `JapaneseDate.atTime()` 方法示例

> 原文：[https://www.geeksforgeks.org/japanesedate-attime-method-in-java-with-example/](https://www.geeksforgeks.org/japanesedate-attime-method-in-java-with-example/)

`java.time.chrono.JapaneseDate` 类的 `atTime()` 方法用于将这个 `JapaneseDate` 与一个 `LocalTime` 相加，产生一个等价的 `ChronoLocalDateTime`。

**语法：**
```java
public final ChronoLocalDateTime atTime(LocalTime localTime)
```

**参数：** 该方法以 `LocalTime` 类型的对象为参数。
**返回值：** 此方法通过将该日本日期与传入的 `LocalTime` 相加，返回一个 `ChronoLocalDateTime`。

以下是举例说明 `atTime()` 方法：

### 示例 1

```java
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
              = LocalTime.now();

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
              "Chrono LocalDateTime is: "
              + date);
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**输出**
```java
Chrono LocalDateTime is: Japanese Heisei 32-03-18T17:18:51.528
```

### 示例 2

```java
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
              = LocalTime.of(8, 20);

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
              "Chrono LocalDateTime is: "
              + date);
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**输出**
```java
Chrono LocalDateTime is: Japanese Heisei 32-03-18T08:20
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#atTime-java.time.LocalTime-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#atTime-java.time.LocalTime-)