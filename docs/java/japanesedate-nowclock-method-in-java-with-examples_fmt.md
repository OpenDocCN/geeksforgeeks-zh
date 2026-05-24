# Java 中的 JapaneseDate nowClock() 方法示例

> 原文：[https://www.geeksforgeeks.org/japanesedate-nowclock-method-in-java-with-examples/](https://www.geeksforgeeks.org/japanesedate-nowclock-method-in-java-with-examples/)

`java.time.chrono.JapaneseDate` 类的 `now()` 方法用于从指定的时钟获取根据日本日历系统的当前日本日期。

**语法：**

```java
public static JapaneseDate now(Clock clock)
```

**参数：** 该方法以 `Clock` 对象为参数，在此基础上形成日本日期。

**返回值：** 此方法从指定的时钟根据日本日历系统返回当前的 `JapaneseDate`。

以下是举例说明 `now()` 方法的例子：

## 示例 1

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemUTC();

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(clock);

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

**输出：**

```java
JapaneseDate: Japanese Heisei 32-03-23
```

## 示例 2

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemDefaultZone();

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(clock);

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

**输出：**

```java
JapaneseDate: Japanese Heisei 32-03-23
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#now-java.time.Clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#now-java.time.Clock-)