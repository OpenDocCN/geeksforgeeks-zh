# Java 中 `Calendar` `getFirstDayOfWeek()` 方法示例

> 原文：[https://www.geeksforgeeks.org/calendar-getfirstdayofweek-method-in-java-with-examples/](https://www.geeksforgeeks.org/calendar-getfirstdayofweek-method-in-java-with-examples/)

`Calendar` 类中的 `getFirstDayOfWeek()` 方法用于返回本日历一周的第一天。

**语法：**
```java
public int getFirstDayOfWeek()
```

**参数：** 该方法不取任何参数。
**返回值：** 该方法返回一周的第一天。

以下程序说明了 `Calendar` 类 `getFirstDayOfWeek()` 方法的工作：

## 示例

```java
// Java code to illustrate
// getFirstDayOfWeek() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String[] args)
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the first
        // day of the week
        System.out.println("The First day"
                           + " is: " + calndr.getFirstDayOfWeek());

        int the_day = calndr.getFirstDayOfWeek();
        switch (the_day) {
        case 1:
            System.out.println("Sunday");
            break;
        case 2:
            System.out.println("Monday");
            break;
        case 3:
            System.out.println("Tuesday");
            break;
        case 4:
            System.out.println("Wednesday");
            break;
        case 5:
            System.out.println("Thursday");
            break;
        case 6:
            System.out.println("Friday");
            break;
        case 7:
            System.out.println("Saturday");
            break;
        }
    }
}
```

**输出：**
```java
The First day is: 1
Sunday
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getFirstDayOfWeek()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getFirstDayOfWeek())