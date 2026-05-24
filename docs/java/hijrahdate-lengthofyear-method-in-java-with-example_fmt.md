# Java 中的 `HijrahDate.lengthOfYear()` 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahdate-lengthofyear-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-lengthofyear-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `lengthOfYear()` 方法用于获取特定 hijrah date 表示的一年中的天数。

**语法：**

```java
public int lengthOfYear()
```

**参数：** 该方法不接受任何参数。

**返回值：** 该方法返回一年中由特定回历日期表示的整数形式的**天数**。

下面举例说明 `lengthOfYear()` 方法：

## 示例 1

```java
// Java program to demonstrate
// lengthOfYear() method

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 23);

            // Getting length of a year
            // by using lengthOfYear() method
            int length = hidate.lengthOfYear();

            // Display the result
            System.out.println("no of day present: "
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
no of day present: 354
```

## 示例 2

```java
// Java program to demonstrate
// lengthOfYear() method

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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // Getting length of a year
            // by using lengthOfYear() method
            int length = hidate.lengthOfYear();

            // Display the result
            System.out.println("no of day present: "
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
no of day present: 355
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#lengthOfYear--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#lengthOfYear--)