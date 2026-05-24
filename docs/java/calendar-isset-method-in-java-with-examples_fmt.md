# Java 中的 Calendar isSet()方法，带示例

> 原文: [https://www.geeksforgeeks.org/calendar-isset-method-in-java-with-examples/](https://www.geeksforgeeks.org/calendar-isset-method-in-java-with-examples/)

`Calendar`类中的`isSet(int calndr_field)`方法用于检查给定的`Calendar`字段是否设置了值。通过内部字段的计算设置值的所有情况都由`get`方法调用触发。

**语法:**

```java
public final boolean isSet(int calndr_field)
```

**参数:** 该方法取一个参数`calndr_field`，指的是要操作的日历字段。
**返回值:** 如果设置了日历字段的值，该方法返回`true`，否则返回`false`。

以下程序说明了`Calendar`类的`isSet()`方法的工作原理:

**示例 1:**

```java
// Java code to illustrate
// isSet() method

import java.util.*;
public class CalendarDemo {
    public static void main(String args[])
    {

        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the calendar object
        System.out.println("The Year is: "
                           + calndr.get(Calendar.YEAR));

        // Querying for the value if set or not
        boolean val = calndr.isSet(Calendar.YEAR);
        System.out.println("Is the"
                           + " Value set? " + val);

        // Clearing the instance
        calndr.clear(Calendar.YEAR);

        // Performing isSet() operation
        val = calndr.isSet(Calendar.YEAR);
        System.out.println("Is the"
                           + " Value set? " + val);
    }
}
```

**Output:**

```java
The Year is: 2019
Is the Value set? true
Is the Value set? false
```

**示例 2:**

```java
// Java code to illustrate
// isSet() method

import java.util.*;
public class CalendarDemo {
    public static void main(String args[])
    {

        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the calendar object
        System.out.println("Todays Day is: "
                           + calndr.get(
                                 Calendar.DAY_OF_MONTH));

        // Querying for the value if set or not
        boolean val
            = calndr.isSet(Calendar.DAY_OF_MONTH);
        System.out.println("Is the"
                           + " Value set? " + val);

        // Clearing the instance
        calndr.clear(Calendar.DAY_OF_MONTH);

        // Performing isSet() operation
        val = calndr.isSet(Calendar.DAY_OF_MONTH);
        System.out.println("Is the"
                           + " Value set? " + val);
    }
}
```

**Output:**

```java
Todays Day is: 21
Is the Value set? true
Is the Value set? false
```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#isSet-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#isSet-int-)