# Java 中带有 DayOfYear()方法的 LocalDateTime，示例

> 原文: [https://www.geeksforgeeks.org/localdatetime-withdayofyear-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withdayofyear-method-in-java-with-examples/)

Java 中 `LocalDateTime` 类的 `withDayOfYear()` 方法用于获取该 `LocalDateTime` 的副本，`DayOfYear` 被更改为 `dayOfYear`，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

## 语法

```java
public LocalDateTime withDayOfYear(int dayOfYear)
```

## 参数

该方法接受一个强制参数 `dayOfYear`，该参数指定要在结果本地日期时间实例中设置的 `dayOfYear`。该日期的值可以从 1 到 366。

## 返回

该函数返回一个 `LocalDateTime` 实例，其中 `dayOfYear` 被更改为 `dayOfYear`，并作为参数传递给该方法。该本地日期时间的其余值保持不变。

## 异常

如果 `dayOfYear` 值无效，函数抛出 `DateTimeException`。

下面的程序说明了 `LocalDateTime.withDayOfYear()` 方法:

### 程序 1

```java
// Program to illustrate the withDayOfYear() method

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

        // Get a new LocalDateTime with dayOfYear 1
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfYear(1));
    }
}
```

### 输出

```java
Original LocalDateTime: 2018-11-30T12:54:35.320
New LocalDateTime: 2018-01-01T12:54:35.320
```

### 程序 2

```java
// Program to illustrate the withDayOfYear() method

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

        // Get a new LocalDateTime with dayOfYear 365
        System.out.println("New LocalDateTime: "
                           + dt.withDayOfYear(365));
    }
}
```

### 输出

```java
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-12-31T10:15:30
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withDayOfYear(int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#withDayOfYear(int))