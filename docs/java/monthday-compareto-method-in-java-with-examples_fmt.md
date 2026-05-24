# Java中的MonthDay compareTo()方法，带示例

> 原文：[https://www.geeksforgeeks.org/monthday-compareto-method-in-java-with-examples/](https://www.geeksforgeeks.org/monthday-compareto-method-in-java-with-examples/)

Java中`MonthDay`类的`compareTo()`方法将这个`MonthDay`与另一个`MonthDay`进行比较。

## 语法

```java
public int compareTo(MonthDay other)
```

## 参数

该方法接受一个参数`other`，该参数指定要比较的其他`MonthDay`，不为`null`。

## 返回

功能返回`比较器值`。它可以是负的，如果它是小的，或者是正的，如果它是大的。

## 异常

如果另一个为`null`，函数抛出`NullPointerException`。

以下程序说明了`MonthDay.compareTo()`方法：

### 程序1

```java
// Program to illustrate the compareTo() method

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
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java

```

### 程序2

```java
// Program to illustrate the compareTo() method

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
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java

```

### 程序3

```java
// Program to illustrate the compareTo() method

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
        MonthDay tm2 = MonthDay.parse("--09-06");

        // Uses the function
        LocalDate dt2 = tm2.atYear(2018);

        // Prints the date
        System.out.println(dt1.compareTo(dt2));
    }
}
```

**输出:**

```java

```

**参考:** [https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#compareTo-java.time.MonthDay-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#compareTo-java.time.MonthDay-)