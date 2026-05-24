# Java 中的 `HijrahDate.now(ZoneId)` 方法示例

> 原文: [https://www.geeksforgeeks.org/hijrahdate-nowzoneid-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-nowzoneid-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `now()` 方法是根据指定区域的 Hijrah 日历系统获取当前的 Hijrah 日期。

**语法:**

```java
public static HijrahDate now(ZoneId zone)
```

**参数**: 该方法以 `ZoneId` 为对象，在此基础上形成 Hijrah 日期。

**返回值:** 该方法根据 Hijrah 系统从指定的时钟返回当前 `HijrahDate`。

以下是举例说明 `now()` 方法的例子:

**例 1:**

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
            // Creating and initializing ZoneId
            ZoneId id = ZoneId.systemDefault();

            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now(id);

            // Display the result
            System.out.println("HijrahDate: "
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

**Output:**

```java
HijrahDate: Hijrah-umalqura AH 1441-06-25
```

**例 2:**

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
            // Creating and initializing ZoneId
            ZoneId id = ZoneId.of("Z");

            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now(id);

            // Display the result
            System.out.println("HijrahDate: "
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

**Output:**

```java
HijrahDate: Hijrah-umalqura AH 1441-06-25
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#now-java.time.ZoneId-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#now-java.time.ZoneId-)