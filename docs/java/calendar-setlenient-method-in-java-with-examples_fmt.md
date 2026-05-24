# Java 中的日历 setLenient() 方法示例

> 原文：`https://www.geeksforgeeks.org/calendar-setlenient-method-in-java-with-examples/`

`Calendar`类中的`setLenient(boolean leniency)`方法用于指定日期和时间的解释是否宽松。

## 语法

```java
public void setLenient(boolean leniency)
```

## 参数
该方法采用布尔类型的一个参数，该参数表示日历的模式。布尔值`true`打开宽松处理模式，`false`关闭宽松处理模式。

## 返回值
该方法不返回值。

以下程序说明了`Calendar`类的`setLenient()`方法的工作：

### 示例 1

```java
// Java code to illustrate
// setLenient() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current
        // mood of leniency
        boolean value = calndr.isLenient();
        System.out.println("Is the"
                           + " Calendar lenient? "
                           + value);

        // Changing the leniency
        calndr.setLenient(false);

        // Displaying the result
        System.out.println("The altered"
                           + " Leniency: "
                           + calndr.isLenient());
    }
}
```

**Output:**

```java
Is the Calendar lenient? true
The altered Leniency: false
```

### 示例 2

```java
// Java code to illustrate
// isLenient() method

import java.util.*;
public class CalendarDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr
            = Calendar.getInstance();

        // Displaying the calendar
        System.out.println("Current Calendar: "
                           + calndr.getTime());

        // Checking the leniency
        boolean leniency = calndr.isLenient();
        calndr.setLenient(false);
        leniency = calndr.isLenient();

        // Displaying the leniency
        System.out.println("Calendar is"
                           + " lenient? "
                           + leniency);

        // Checking the leniency
        calndr.setLenient(true);
        leniency = calndr.isLenient();

        // Displaying the leniency
        System.out.println("Calendar is"
                           + " lenient: "
                           + leniency);
    }
}
```

**Output:**

```java
Current Calendar: Thu Feb 21 11:00:50 UTC 2019
Calendar is lenient? false
Calendar is lenient: true
```

## 参考
`https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#setLenient-boolean-`