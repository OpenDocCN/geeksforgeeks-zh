# Java 中的 LocalDate isBefore()方法，示例

> 原文: [https://www.geeksforgeeks.org/localdate-isbefore-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-isbefore-method-in-java-with-examples/)

Java 中 `LocalDate` 类的 `isBefore()` 方法检查该日期是否在指定日期之前。

**语法**:

```java
public boolean isBefore(ChronoLocalDate date2)
```

**参数**: 该方法接受单个强制参数 `date2`，即要进行比较的其他日期，不可为空。

**返回值**: 如果该日期在指定日期之前，则函数返回 `true`。

下面的程序说明了 Java 中 `LocalDate` 的 `isBefore()` 方法:

**程序 1** :

## 示例 1

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2017-11-27");

        // Checks
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**Output:**

```java
false
```

**程序 2** :

## 示例 2

```java
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2019-11-27");

        // Checks
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**Output:**

```java
true
```

**参考**: [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isBefore(java.time.chrono.ChronoLocalDate)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isBefore(java.time.chrono.ChronoLocalDate))