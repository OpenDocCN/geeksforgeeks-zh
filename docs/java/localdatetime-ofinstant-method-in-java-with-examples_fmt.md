# Java 中的 LocalDateTime ofInstant()方法，示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-ofinstant-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofinstant-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `ofInstant()` 方法用于使用一个 `Instant` 和区域 `ZoneId` 创建 `LocalDateTime` 的一个实例。这两个参数被传递给方法，方法根据这两个参数返回 `LocalDateTime`。本地日期时间的计算遵循以下步骤。

*   时区标识和 `Instant` 用于获取与协调世界时/格林尼治标准时间的偏移量，因为每个实例只能有一个有效的偏移量。
*   最后，使用 `Instant` 和获得的偏移量计算本地日期和时间。

## 语法

```java
public static LocalDateTime 
       ofInstant(Instant instant,
                 ZoneId zone)
```

## 参数

该方法接受两个参数：

*   `instant` – 它是一个 `Instant` 类型，表示创建 `LocalDateTime` 时经过的时刻。
*   `zone` – 它属于时区标识类型，表示用于创建偏移量的时区。

## 返回值

该方法返回 `LocalDateTime`。

## 异常

如果结果超出支持范围，该方法抛出 `DateTimeException`。

## 程序 1

下面的程序说明了 Java 中的 `ofInstant(Instant instant, ZoneId zone)` 方法：

```java
// Java program to demonstrate
// LocalDateTime.ofInstant(
// Instant instant, ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print full date
        System.out.println(
            "Date: " + localdatetime);
    }
}
```

## 输出

```java
Date: 2020-05-13T12:40:38.087
```

## 程序 2

```java
// Java program to demonstrate
// LocalDateTime.ofInstant(
// Instant instant, ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create LocalDateTime object
        LocalDateTime localdatetime
            = LocalDateTime.ofInstant(
                Instant.now(),
                ZoneId.systemDefault());

        // Print year only
        System.out.println(
            "Year: " + localdatetime.getYear());
    }
}
```

## 输出

```java
Year: 2020
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#ofInstant(java.time.Instant, java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#ofInstant(java.time.Instant, java.time.ZoneId))