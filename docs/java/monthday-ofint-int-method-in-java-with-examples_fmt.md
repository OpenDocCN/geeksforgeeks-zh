# Java 中 `MonthDay.of(int, int)` 方法的示例

> 原文：[https://www.geeksforgeeks.org/monthday-ofint-int-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-ofint-int-method-in-java-with-examples/)

`MonthDay` 类中的 `of(int, int)` 方法用于获取 `MonthDay` 的实例。

## 语法

```java
public static MonthDay of(
     int month, int dayOfMonth)
```

## 参数

该方法接受两个参数：

*   `month`：代表一年中的月份。
*   `dayOfMonth`：表示一个月中的某一天。

## 返回值

此方法返回 `MonthDay`。

## 异常

如果任何字段的值超出范围或该月的某一天对该月无效，该方法将抛出 `DateTimeException`。

下面的程序说明了 Java 中 `MonthDay` 的 `of(int, int)` 方法：

## 程序 1

```java
// Java program to demonstrate
// MonthDay.of(int, int) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(int, int) method
        // of MonthDay class
        MonthDay monthday = MonthDay.of(5, 9);

        // print both month and day
        System.out.println("MonthDay: "
                           + monthday);
    }
}
```

**Output:**

```java
MonthDay: --05-09
```

## 程序 2

```java
// Java program to demonstrate
// MonthDay.of(int, int) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(int, int) method
        // of MonthDay class
        MonthDay monthday = MonthDay.of(5, 9);

        // print only month
        System.out.println("Month: "
                           + monthday.getMonth());
    }
}
```

**Output:**

```java
Month: MAY
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#of(int, int)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#of(int, int))