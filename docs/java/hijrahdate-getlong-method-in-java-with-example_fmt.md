# Java 中的 HijrahDate getLong() 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahdate-getlong-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-getlong-method-in-java-with-example/)

`HijrahDate` 类的 `getLong()` 方法用于以长格式（`long`）检索传递的时态字段。

**语法：**

```java
public long getLong(TemporalField field)
```

**参数：** 该方法以任意类型的 `TemporalField` 为参数。

**返回值：** 该方法以长格式返回传递的时态字段。

以下是说明 `getLong()` 方法的例子：

## 示例 1

```java
// Java program to demonstrate
// getLong() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(ChronoField.EPOCH_DAY);

            // display the result
            System.out.println(
                "specified temporal field"
                + "in long format: "
                + tempo);
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
specified temporal fieldin long format: 18304
```

## 示例 2

```java
// Java program to demonstrate
// getLong() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(ChronoField.DAY_OF_WEEK);

            // display the result
            System.out.println("specified temporal field"
                               + " in long format: "
                               + tempo);
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
specified temporal field in long format: 3
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#getLong-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#getLong-java.time.temporal.TemporalField-)