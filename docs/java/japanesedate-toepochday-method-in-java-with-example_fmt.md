# Java 中的 `JapaneseDate` `toEpochDay()` 方法示例

> 原文：[https://www.geeksforgeks.org/japanesedate-toepochday-method-in-java-with-example/](https://www.geeksforgeks.org/japanesedate-toepochday-method-in-java-with-example/)

`java.time.chrono.JapaneseDate` 类的 `toEpochDay()` 方法用于获取当前日本日期和 `1970-01-01` 之间存在的纪元天数。

**语法：**

```java
public long toEpochDay()
```

**参数：** 该方法不接受任何参数。

**返回值：** 此方法返回当前回历日期和 `1389-10-22` 之间存在的纪元天数。

以下是举例说明 `toEpochDay()` 方法的例子：

### 示例 1

```java
// Java program to demonstrate
// toEpochDay() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // Getting no of ephoch days present
            // by using toEpochDay() method
            long length = hidate.toEpochDay();

            // Display the result
            System.out.println("EpochDay : "
                               + length);
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
EpochDay : 18365
```

### 示例 2

```java
// Java program to demonstrate
// toEpochDay() method

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
                = JapaneseDate.of(1970, 01, 01);

            // Getting no of ephoch days present
            // by using toEpochDay() method
            long length = hidate.toEpochDay();

            // Display the result
            System.out.println("EpochDay : "
                               + length);
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
EpochDay : 0
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#toEpochDay--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#toEpochDay--)