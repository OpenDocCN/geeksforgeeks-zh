# Java 中的 HijrahDate isLeapYear() 方法示例

> 原文：[https://www.geeksforgeeks.org/hijrahdate-isleapyear-method-in-java-with-example/](https://www.geeksforgeeks.org/hijrahdate-isleapyear-method-in-java-with-example/)

`Java.time.chrono.HijrahDate` 类的 `isLeapYear()` 方法用于区分闰年和非闰年。如果这个 `HijrahDate` 代表的年份是闰年，这个方法将返回 `true`，否则返回 `false`。

## 语法

```java
public boolean isLeapYear()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回 `boolean` 值，即如果当前年份是闰年则为 `true`，否则为 `false`。

## 示例

以下是说明该方法的示例：

### 示例 1

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
        // Creating and initializing
        // HijrahDate Object
        HijrahDate hidate
            = HijrahDate.of(1398, 03, 23);

        System.out.println("HijrahDate: "
                           + hidate.toString());

        // Checking if the date is leap year or not
        // by using isLeapYear() method
        boolean flag = hidate.isLeapYear();

        // Display the result
        if (flag)
            System.out.println("Leap year");
        else
            System.out.println("Not a leap year");
    }
}
```

**输出：**

```java
HijrahDate: Hijrah-umalqura AH 1398-03-23
Not a leap year
```

### 示例 2

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
        // Creating and initializing
        // HijrahDate Object
        HijrahDate hidate = HijrahDate.now();

        System.out.println("HijrahDate: "
                           + hidate.toString());

        // Checking if the date is leap year or not
        // by using isLeapYear() method
        boolean flag = hidate.isLeapYear();

        // Display the result
        if (flag)
            System.out.println("Leap year");
        else
            System.out.println("Not a leap year");
    }
}
```

**输出：**

```java
HijrahDate: Hijrah-umalqura AH 1441-06-25
Leap year
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#isLeapYear--](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#isLeapYear--)