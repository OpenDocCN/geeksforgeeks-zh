# Java 中的 Calendar getTime()方法，带示例

> 原文：[https://www.geeksforgeeks.org/calendar-gettime-method-in-java-with-examples/](https://www.geeksforgeeks.org/calendar-gettime-method-in-java-with-examples/)

`Calendar`类中的`getTime()`方法用于返回一个类似于由该`Calendar`的时间值表示的日期的对象。

**语法：**
```java
public final Date getTime()
```

**参数：** 该方法不取任何参数。
**返回值：** 该方法返回日期，用本日历表示。

以下程序说明了`Calendar`类`getTime()`方法的工作：

## 示例 1

```java
// Java code to illustrate
// getTime() method

import java.util.*;

public class Calendar_Demo {

    public static void main(String args[])
        throws InterruptedException
    {

        // Creating a calendar
        Calendar calndr1
            = Calendar.getInstance();

        // Displaying the current time
        System.out.println("The Current"
                           + " Time is: "
                           + calndr1.getTime());

        // Adding few delay
        Thread.sleep(10000);

        // Creating another calendar
        Calendar calndr2 = Calendar.getInstance();

        // Displaying the upcoming time
        Date dt = calndr2.getTime();
        System.out.println("The upcoming"
                           + " time is: " + dt);
    }
}
```

**Output：**
```java
The Current Time is: Wed Feb 20 14:40:37 UTC 2019
The upcoming time is: Wed Feb 20 14:40:47 UTC 2019
```

## 示例 2

```java
// Java code to illustrate
// getTime() method

import java.util.*;

public class Calendar_Demo {

    public static void main(String args[])
        throws InterruptedException
    {

        // Creating a calendar
        Calendar calndr1
            = Calendar.getInstance();

        // Displaying the current time
        System.out.println("The Current"
                           + " Time is: "
                           + calndr1.getTime());

        // Adding few delay
        Thread.sleep(5000);

        // Creating another calendar
        Calendar calndr2 = Calendar.getInstance();

        // Displaying the upcoming time
        Date dt = calndr2.getTime();
        System.out.println("The upcoming"
                           + " time is: " + dt);
    }
}
```

**Output：**
```java
The Current Time is: Wed Feb 20 14:40:50 UTC 2019
The upcoming time is: Wed Feb 20 14:40:55 UTC 2019
```

**参考：** [https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getMaximum-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#getMaximum-int-)