# Java 中 LocalTime from()方法示例

> 原文：[https://www.geeksforgeeks.org/localtime-from-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-from-method-in-java-with-examples/)

`LocalTime`类的`from()`方法有助于从作为参数传递给方法的`TemporalAccessor`对象中获取`LocalTime`的实例。`TemporalAccessor`代表一组任意的日期和时间信息，该方法有助于根据指定的`TemporalAccessor`对象获取`LocalTime`。

## 语法

```java
public static LocalTime from(TemporalAccessor temporal)
```

## 参数

该方法接受单个参数`temporal`，即`TemporalAccessor`对象。它不应为`null`。

## 返回值

该方法从`TemporalAccessor`对象返回`LocalTime`，不为`null`。

## 异常

如果无法转换为`LocalTime`，该方法抛出`DateTimeException`。

下面的程序说明了`from()`方法：

### 程序 1

```java
// Java program to demonstrate
// LocalTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a ZonedDateTime object
        ZonedDateTime zonedDateTime
            = ZonedDateTime.now();

        // apply from()
        LocalTime value
            = LocalTime.from(zonedDateTime);

        // print result
        System.out.println("LocalTime value : "
                           + value);
    }
}
```

**输出：**

```java
LocalTime value : 06:17:32.760
```

### 程序 2

```java
// Java program to demonstrate
// LocalTime.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a OffsetDateTime object
        OffsetDateTime offset
            = OffsetDateTime.now();

        // apply from()
        LocalTime value = LocalTime.from(offset);

        // print result
        System.out.println("LocalTime value : "
                           + value);
    }
}
```

**输出：**

```java
LocalTime value : 06:17:35.131
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#from(java.time.temporal.TemporalAccessor)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#from(java.time.temporal.TemporalAccessor))