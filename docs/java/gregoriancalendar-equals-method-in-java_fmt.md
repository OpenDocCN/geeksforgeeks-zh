# Java 中的 GregorianCalendar equals() 方法

> 原文: [https://www.geeksforgeeks.org/gregoriancalendar-equals-method-in-java/](https://www.geeksforgeeks.org/gregoriancalendar-equals-method-in-java/)

`java.util.GregorianCalendar.equals()` 方法是 Java 中的内置函数，它检查这个 `GregorianCalendar` 实例和作为参数传递给函数的对象之间的相等性。只有当指定的对象是一个具有与这个公历日历对象实例相同的时间值（从纪元的毫秒偏移）的公历日历对象时，它才返回真。

## 语法

```java
public boolean equals(Object obj)
```

## 参数

该函数接受单个强制参数 `Object obj`，该参数将与这个 `GregorianCalendar` 实例进行比较。

## 返回值

只有当指定的对象是一个 `GregorianCalendar` 对象并且具有与这个实例相同的时间值（从纪元开始的毫秒偏移）时，该方法才返回 `true`，否则返回 `false`。

## 示例

```java
Input : c1 = Mon Jul 23 23:46:14 UTC 2018, c2 = Mon Jul 23 23:46:14 UTC 2018
Output : true

Input : c1 = Mon Jul 23 23:46:14 UTC 2018, c2 = Sun Jul 24 00:02:52 UTC 2022
Output : false
```

下面的程序说明了 `java.util.GregorianCalendar.equals()` 函数：

### 程序 1

```java
// Java Program to illustrate the equals() function
// of GregorianCalendar class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar c1 = (GregorianCalendar)
                     GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + c1.getTime());

        // Create a second calendar equal to first one
        GregorianCalendar c2 =
              (GregorianCalendar)(Calendar)c1.clone();

        // Compare the two calendars
        System.out.println("Both calendars are equal:"
                           + c1.equals(c2));

        // Adding 15 months to second calendar
        c2.add(GregorianCalendar.MONTH, 15);

        // Display the current date and time
        System.out.println("Modified Date and Time : "
                           + c2.getTime());

        // Compare the two calendars
        System.out.println("Both calendars are equal:"
                           + c1.equals(c2));
    }
}
```

**Output:**

```java
Current Date and Time : Fri Jul 27 12:05:05 UTC 2018
Both calendars are equal:true
Modified Date and Time : Sun Oct 27 12:05:05 UTC 2019
Both calendars are equal:false
```

### 程序 2

```java
// Java Program to illustrate the equals() function
// of GregorianCalendar class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a new calendar
        GregorianCalendar c1 = (GregorianCalendar)
                     GregorianCalendar.getInstance();

        // Display the current date and time
        System.out.println("Current Date and Time : "
                           + c1.getTime());

        // Create a second calendar equal to first one
        GregorianCalendar c2 =
             (GregorianCalendar)(Calendar)c1.clone();

        // Compare the two calendars
        System.out.println("Both calendars are equal:"
                           + c1.equals(c2));

        // Changing the Time Zone of c2
        c2.setTimeZone(TimeZone.getTimeZone("CST"));

        // Compare the two calendars
        System.out.println("Both calendars are equal:"
                           + c1.equals(c2));
    }
}
```

**Output:**

```java
Current Date and Time : Fri Jul 27 12:05:08 UTC 2018
Both calendars are equal:true
Both calendars are equal:false
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#equals()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#equals())