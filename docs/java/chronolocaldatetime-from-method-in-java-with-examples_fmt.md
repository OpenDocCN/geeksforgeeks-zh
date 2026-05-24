# Java 中的 ChronoLocalDateTime from()方法，示例

> 原文：[https://www.geeksforgeeks.org/chronolocaldatetime-from-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-from-method-in-java-with-examples/)

`ChronoLocalDateTime`接口的`from()`方法用于从作为参数传递的时态对象中获取`ChronoLocalDateTime`的实例。

## 语法：

```java
static ChronoLocalDateTime<T> from(TemporalAccessor temporal)
```

## 参数：
该方法接受一个参数`temporal`，该参数指定要转换为`ChronoLocalDateTime`实例的时态对象。它不应为`null`。

## 返回：
函数返回从时态对象转换而来的`ChronoLocalDateTime`。

## 异常：
程序抛出`DateTimeException`，如果无法将给定的时态对象转换为`ChronoLocalDateTime`，则会抛出该异常。

下面的程序说明了`ChronoLocalDateTime.from()`方法：

## 程序 1：

```java
// Program to illustrate the from() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        ChronoLocalDateTime date
            = LocalDateTime
                  .from(ZonedDateTime.now());

        System.out.println(date);
    }
}
```

## 输出：

```java
2019-05-29T11:53:52.135
```

## 参考：
[https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#from-java.time.temporal.TemporalAccessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#from-java.time.temporal.TemporalAccessor-)