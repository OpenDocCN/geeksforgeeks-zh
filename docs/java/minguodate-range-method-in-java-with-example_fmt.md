# Java 中的 MinguoDate range()方法，示例

> 原文：[https://www.geeksforgeeks.org/minguodate-range-method-in-java-with-example/](https://www.geeksforgeeks.org/minguodate-range-method-in-java-with-example/)

`java.time.chrono.MinguoDate`类的`range()`方法用于从`TemporalField`类型的指定字段中获取的范围。

**语法：**

```java
public ValueRange range(TemporalField field)
```

**参数：** 该方法将`TemporalField`类型的`field`作为要获取其范围的参数。

**返回值：** 该方法以`ValueRange`的形式返回指定字段的`range`。

以下是说明`range()`方法的示例：

## 示例 1

```java
// Java program to demonstrate
// range() method

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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // Getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = hidate.range(ChronoField.ERA);

            // display the result
            System.out.println("Equivalent Range : "
                               + range);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output：**

```java
Equivalent Range : 0 - 1
```

## 示例 2

```java
// Java program to demonstrate
// range() method

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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // Getting the ValueRange for
            // given ChronoField
            // by using range() method
            ValueRange range
                = hidate.range(ChronoField.YEAR);

            // display the result
            System.out.println("Equivalent Range : "
                               + range);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output：**

```java
Equivalent Range : -1000001910 - 999998088
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#range-java.time.temporal.TemporalField-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#range-java.time.temporal.TemporalField-)