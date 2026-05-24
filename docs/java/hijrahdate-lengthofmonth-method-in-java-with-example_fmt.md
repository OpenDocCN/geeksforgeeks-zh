# Java 中的 HijrahDate lengthOfMonth() 方法示例

> 原文: [https://www.geeksforgeeks.org/hijrahdate-lengthofmonth-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-lengthofmonth-method-in-java-with-example/)

`java.time.chrono.HijrahDate` 类的 `lengthOfMonth()` 方法用于获取特定 hijrah date 表示的一个月中的天数。

## 语法

```java
public int lengthOfMonth()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个月中某个特定回历日期所代表的天数。

以下是说明 `lengthOfMonth()` 方法的示例:

## 示例 1

```java
// Java program to demonstrate
// lengthOfMonth() method

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

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

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

**输出:**

```java
no of day present: 30
```

## 示例 2

```java
// Java program to demonstrate
// lengthOfMonth() method

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

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

            // display the result
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

**输出:**

```java
no of day present: 29
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#hashCode--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#hashCode--)