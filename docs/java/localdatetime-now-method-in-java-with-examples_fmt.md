# Java 中的 LocalDateTime now() 方法示例

> 原文：[https://www.geeksforgeeks.org/localdatetime-now-method-in-java-with-examples/](https://www.geeksforgeeks.org/localdatetime-now-method-in-java-with-examples/)

在 `LocalDateTime` 类中，根据传递给它的参数，有三种 `now()` 方法。

## now()

`now()` 是 `LocalDateTime` 类的一个方法，用于从默认时区的系统时钟中获取当前日期时间。此方法将根据系统时钟和默认时区返回本地日期时间，以获取当前日期时间。

**语法：**

```java
public static LocalDateTime now()
```

**参数：** 该方法不接受参数。

**返回值：** 此方法使用系统时钟返回当前日期时间。

下面的程序说明了 `now()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create an LocalDateTime object
        LocalDateTime lt = LocalDateTime.now();

        // print result
        System.out.println("LocalDateTime : " + lt);
    }
}
```

**输出：**

```java
LocalDateTime : 2019-01-21T05:47:08.644
```

## now(Clock)

`now(Clock clock)` 是 `LocalDateTime` 类的一个方法，用于根据作为参数传递的指定时钟返回当前日期时间。

**语法：**

```java
public static LocalDateTime now(Clock clock)
```

**参数：** 该方法接受 `Clock` 作为参数，该参数是要使用的时钟。

**返回值：** 此方法返回当前日期时间。

下面的程序说明了 `now(Clock)` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a clock
        Clock cl = Clock.systemUTC();

        // create an LocalDateTime object using now(Clock)
        LocalDateTime lt = LocalDateTime.now(cl);

        // print result
        System.out.println("LocalDateTime : " + lt);
    }
}
```

**输出：**

```java
LocalDateTime : 2019-01-21T05:47:20.949
```

## now(ZoneId)

`now(ZoneId zone)` 是 `LocalDateTime` 类的一个方法，用于从指定时区的系统时钟返回作为参数传递的当前日期时间。指定时区避免了对默认时区的依赖。

**语法：**

```java
public static LocalDateTime now(ZoneId zone)
```

**参数：** 该方法接受 `ZoneId` 作为参数，该参数是要使用的区域。

**返回值：** 此方法返回当前日期时间。

下面的程序说明了 `now(ZoneId)` 方法：

**程序 1：**

```java
// Java program to demonstrate
// LocalDateTime.now() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a clock
        ZoneId zid = ZoneId.of("Europe/Paris");

        // create an LocalDateTime object using now(zoneId)
        LocalDateTime lt = LocalDateTime.now(zid);

        // print result
        System.out.println("LocalDateTime : " + lt);
    }
}
```

**输出：**

```java
LocalDateTime : 2019-01-21T06:47:22.756
```

**参考文献：**
- [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now())
- [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now(java.time.Clock)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now(java.time.Clock))
- [https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now(java.time.ZoneId)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#now(java.time.ZoneId))