# Java 中 Calendar getMinimalDaysInFirstWeek() 方法，带示例

> 原文: [https://www.geeksforgeeks.org/calendar-getminimaldaysinfirstweek-method-in-java-with-examples/](https://www.geeksforgeeks.org/calendar-getminimaldaysinfirstweek-method-in-java-with-examples/)

`Calendar` 类中的 `getMinimalDaysInFirstWeek()` 方法用于返回所需年份第一周所需的最小天数。

**语法:**

```java
public int getMinimalDaysInFirstWeek()
```

**参数:** 该方法不取任何参数。

**返回值:** 该方法返回次年第一周所需的最小天数。

以下程序说明了 `Calendar` 类的 `getMinimalDaysInFirstWeek()` 方法的工作:

**示例 1:**

```java
// Java code to illustrate
// getMinimalDaysInFirstWeek() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr
            = new GregorianCalendar(2018, 6, 10);

        // Getting the required minimal days
        int min_days
            = calndr.getMinimalDaysInFirstWeek();

        // Displaying the results
        System.out.println("The Minimal"
                           + " days required: "
                           + min_days);
    }
}
```

**Output:**

```java
The Minimal days required: 1
```

**示例 2:**

```java
// Java code to illustrate
// getMinimalDaysInFirstWeek() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Getting the required minimal days
        int min_days
            = calndr.getMinimalDaysInFirstWeek();

        // Displaying the results
        System.out.println("The Minimal"
                           + " days required: "
                           + min_days);
    }
}
```

**Output:**

```java
The Minimal days required: 1
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getMinimalDaysInFirstWeek--](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getMinimalDaysInFirstWeek--)