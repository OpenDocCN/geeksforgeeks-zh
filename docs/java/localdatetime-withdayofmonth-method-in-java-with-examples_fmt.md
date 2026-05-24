# Java 中带有 `withDayOfMonth()` 方法的 `LocalDateTime`，示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-withdayofmonth-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withdayofmonth-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `withDayOfMonth()` 方法用于获取该 `LocalDateTime` 的副本，`DayOfMonth` 更改为 `dayOfMonth` 作为参数传递给该方法。该本地日期时间的其余值保持不变。

## 语法

```java
public LocalDateTime withDayOfMonth(int dayOfMonth)
```

## 参数

此方法接受单个强制参数 `dayOfMonth`，该参数指定了要在结果 `LocalDateTime` 实例中设置的日期月。这个日期的值可以从 1 到 31。

## 返回

该函数返回一个 `LocalDateTime` 实例，将日期月更改为 `dayOfMonth` 作为参数传递给该方法。该本地日期时间的其余值保持不变。

## 异常

如果 `dayOfMonth` 的值无效，函数会抛出 `DateTimeException`。

下面的程序说明了 `LocalDateTime.withDayOfMonth()` 方法：

## 程序 1

```java
// Program to illustrate the withDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with dayOfMonth 25
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfMonth(25));
    }
}
```

## 输出

```java
Original LocalDateTime: 2018-11-30T10:38:27.429
New LocalDateTime: 2018-11-25T10:38:27.429
```

## 程序 2

```java
// Program to illustrate the withDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2015-04-06T10:15:30");

        // Get the String representation of this LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Get a new LocalDateTime with dayOfMonth 1
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfMonth(1));
    }
}
```

## 输出

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-04-01T10:15:30
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withDayOfMonth(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withDayOfMonth(int))