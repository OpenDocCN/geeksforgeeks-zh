# Java 中的 LocalDate ofInstant()方法，示例

> 原文: [https://www.geeksforgeeks.org/localdate-ofinstant-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdate-ofinstant-method-in-java-with-examples/)

Java 中 `LocalDate` 类的 `ofInstant(Instant instant, ZoneId zone)` 方法用于从 `Instant` 和 `ZoneId` 创建 `LocalDate` 的实例。这两个参数被传递给方法，并在此基础上创建一个 `LocalDate` 实例。本地日期的计算遵循以下步骤。

1.  区域标识和时刻用于获取从世界协调时/格林威治时间的偏移，因为每个实例只能有一个有效的偏移。
2.  最后，使用瞬间和获得的偏移计算本地日期。

## 语法

```java
public static LocalDate 
       ofInstant(Instant instant,
                 ZoneId zone)
```

## 参数

该方法接受两个参数:

*   `instant`: 属于 `Instant` 类型，代表创建日期所经过的瞬间。
*   `zone`: `ZoneId` 类型，代表偏移量。

## 返回值

此方法返回 `LocalDate`。

## 异常

如果结果超出支持范围，该方法抛出 `DateTimeException`。

## 注意

该方法只包含在最新版本的 Java 中的 `LocalDate` 类中，因此可能不会在少数在线编译器中运行。

下面的程序说明了 Java 中的 `ofInstant(Instant instant, ZoneId zone)` 方法:

### 程序 1

```java
// Java program to demonstrate
// LocalDate.ofInstant(
// Instant instant, ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        LocalDate localdate
            = LocalDate.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print full date
        System.out.println("Date: "
                           + localdate);
    }
}
```

**Output:**

```java
Date: 2020-05-13
```

### 程序 2

```java
// Java program to demonstrate
// LocalDate ofInstant() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDate object
        LocalDate localdate
            = LocalDate.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print year only
        System.out.println(
            "Year: "
            + localdate.getYear());
    }
}
```

**Output:**

```java
Year: 2020
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#ofInstant(java.time.Instant, java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#ofInstant(java.time.Instant, java.time.ZoneId))