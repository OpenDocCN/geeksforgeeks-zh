# Java 中的 MonthDay isBefore() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/monthday-isbefore-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-isbefore-method-in-java-with-examples/)

`MonthDay` 类的 `isBefore()` 方法，用于检查该 `MonthDay` 是否在作为参数传递的 `MonthDay` 之前。此方法返回一个布尔值，显示比较结果。

## 语法

```java
public boolean isBefore(MonthDay other)
```

## 参数

此方法接受一个参数 `other`，即要比较的另一个 `MonthDay`。

## 返回值

如果这个 `MonthDay` 在指定的 `MonthDay` 之前，这个方法返回 `true`，否则返回 `false`。

以下程序说明了 `isBefore()` 方法：

### 程序 1

```java
// Java program to demonstrate
// MonthDay.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--11-12");

        // apply isBefore() method
        boolean value = month.isBefore(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is before monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```java
monthday:--10-12 is before monthday:--11-12 = true
```

### 程序 2

```java
// Java program to demonstrate
// MonthDay.isBefore() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // create other MonthDay object
        MonthDay othermonth = MonthDay.parse("--09-12");

        // apply isBefore() method
        boolean value = month.isBefore(othermonth);

        // print instance
        System.out.println("monthday:"
                           + month + " is before monthday:"
                           + othermonth + " = "
                           + value);
    }
}
```

**Output:**

```java
monthday:--10-12 is before monthday:--09-12 = false
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isBefore(java.time.MonthDay)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#isBefore(java.time.MonthDay))