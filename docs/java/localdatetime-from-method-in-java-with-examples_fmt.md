# Java 中 `LocalDateTime` `from()` 方法示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-from-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-from-method-in-java-with-examples/)

`LocalDateTime` 类的 `from()` 方法用于从作为参数传递的时态对象中获取 `LocalDateTime` 的实例。

## 语法

```java
public static LocalDateTime
    from(TemporalAccessor temporal)
```

## 参数

该方法接受一个参数 `temporal`，该参数指定要转换为本地日期时间实例的时态对象。它不应为 `null`。

## 返回

函数返回 `LocalDateTime`，这是从时态对象转换而来的本地日期时间。

## 异常

程序抛出 `DateTimeException`，如果无法将给定日期转换为本地日期时间，则会抛出该异常。

下面的程序说明了 `LocalDateTime.from()` 方法：

## 程序 1

```java
// Program to illustrate the from() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime date
            = LocalDateTime
                  .from(ZonedDateTime.now());

        System.out.println(date);
    }
}
```

## 输出

```java
2018-11-30T07:53:17.939
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#from(java.time.temporal.TemporalAccessor)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#from(java.time.temporal.TemporalAccessor))