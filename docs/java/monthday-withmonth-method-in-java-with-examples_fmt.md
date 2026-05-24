# MonthDay withMonth()方法（Java示例）

> 原文：[https://www.geeksforgeeks.org/monthday-withmonth-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-withmonth-method-in-java-with-examples/)

`withMonth(int month)`方法属于`MonthDay`类，用于使用作为参数传递的月份来更改`MonthDay`对象中的月份部分，然后该方法返回更改后的`MonthDay`的副本。如果某月某日对于指定的月份无效，则该日将被调整为该月的最后一个有效日期。此实例是不可变的，不受此方法调用的影响。

## 语法

```java
public MonthDay withMonth(int month)
```

## 参数

该方法接受`month`作为参数，该参数是返回的`MonthDay`中设置的月份，从1（一月）到12（十二月）。

## 返回值

该方法返回一个基于原始`MonthDay`与请求月份的新`MonthDay`。

## 异常

如果月份值无效，该方法抛出`DateTimeException`。

下面的程序说明了`withMonth()`方法：

### 程序1

```java
// Java program to demonstrate
// MonthDay.withMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(8, 28);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply withMonth method of MonthDay class
        MonthDay updatedlocal = monthday.withMonth(1);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
MonthDay before applying method: --08-28
MonthDay after applying method: --01-28
```

### 程序2

```java
// Java program to demonstrate
// MonthDay.withMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(10, 31);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply withMonth method of MonthDay class
        MonthDay updatedlocal = monthday.withMonth(5);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**输出：**

```java
MonthDay before applying method: --10-31
MonthDay after applying method: --05-31
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#withMonth(int)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#withMonth(int))