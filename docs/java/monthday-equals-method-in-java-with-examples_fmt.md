# Java 中的 `MonthDay.equals()` 方法示例

> 原文：[https://www.geeksforgeeks.org/monthday-equals-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-equals-method-in-java-with-examples/)

Java 中的 `MonthDay` 类的 `equals()` 方法检查这个 `MonthDay` 是否等于另一个 `MonthDay`。

## 语法

```java
public boolean equals(Object obj)
```

## 参数

这个方法接受一个参数 `obj`，这个参数指定这个 `MonthDay` 是否等于另一个 `MonthDay`。

## 返回值

如果这个时间等于另一个时间，函数返回 `true`。

以下程序说明了 `MonthDay.equals()` 方法：

### 程序 1

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Parses the date
        MonthDay tm2 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.equals(dt2));
    }
}
```

**输出：**

```java
true
```

### 程序 2

```java
// Program to illustrate the equals() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        MonthDay tm1 = MonthDay.parse("--10-06");

        // Uses the function
        LocalDate dt1 = tm1.atYear(2018);

        // Parses the date
        MonthDay tm2 = MonthDay.parse("--12-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.equals(dt2));
    }
}
```

**输出：**

```java
false
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#equals-java.lang.Object-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#equals-java.lang.Object-)