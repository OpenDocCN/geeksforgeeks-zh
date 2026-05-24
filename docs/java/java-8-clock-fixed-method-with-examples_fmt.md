# Java 8 Clock.fixed()方法，带示例

> 原文：[https://www.geeksforgeeks.org/java-8-clock-fixed-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-fixed-method-with-examples/)

`Clock`类是Java日期时间API的一部分。Java日期时间API是从Java版本8中添加的。

`Clock`类的`fixed()`方法返回一个`Clock`对象，该对象返回相同的瞬间。通过调用`Clock.fixed(参数)`返回`Clock`对象，只返回使用参数指定的相同时刻。返回的类对象是不可变的、线程安全的和可序列化的。这种方法的主要用途是在测试时，需要的时钟固定在当前时钟的位置。

## 语法

```java
public static Clock fixed(Instant fixedInstant, ZoneId zone)
```

## 参数

该方法取两个强制参数：

*   `fixedInstant` – 创建时钟对象的`Instant`对象。它不能为空。
*   `zone` – 时钟对象的时区。它不能为空。

## 返回值

此方法返回返回相同瞬间的`Clock`对象。

## 示例

```java
Input:: 
Instance object as parameter : Instant.parse("2018-08-19T16:45:42.00Z");
TimeZone Object as parameter : ZoneId.of("Asia/Calcutta");

Output::
class object:

Explanation:: 
when Clock.fixed(Instant.parse("2018-08-19T16:45:42.00Z") is called, 
then the fixed() method will return a clock object
in return with fixed time zone and instance.
```

下面的程序说明了`java.time.Clock`类的`fixed()`方法：

### 程序 1：定义区域时使用`fixed()`

```java
// Java program to demonstrate
// fixed() method of Clock class

import java.time.*;

// create class
public class fixedMethodDemo {

// Main method
    public static void main(String[] args)
    {

// create instance of clock class
        Instant instant = Instant.parse("2018-08-19T16:02:42.00Z");

// create ZoneId object for Asia/Calcutta zone
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

// call fixed method
        Clock clock = Clock.fixed(instant, zoneId);

// print details of clock
        System.out.println(clock.toString());
    }
}
```

### Output

```java
FixedClock[2018-08-19T16:02:42Z, Asia/Calcutta]
```

### 程序 2：使用`fixed()`作为默认区域

```java
// Java program to demonstrate 
// fixed() method of Clock class

import java.time.*;

// create class
public class fixedMethodDemo {

// Main method
    public static void main(String[] args)
    {
        // create instance of clock class
        Instant instant = Instant.now();

// create ZoneId for defaultZone which is UTC
        ZoneId zoneId = ZoneId.systemDefault();

// call fixed method
        Clock clock = Clock.fixed(instant, zoneId);

// print details of clock
        System.out.println(clock.toString());
    }
}
```

### Output

```java
FixedClock[2018-08-21T08:10:32.498Z, Etc/UTC]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#fixed-java.time.Instant-java.time.ZoneId-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#fixed-java.time.Instant-java.time.ZoneId-)