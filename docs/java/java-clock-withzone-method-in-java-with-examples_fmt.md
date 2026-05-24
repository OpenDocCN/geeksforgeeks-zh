# Java Clock.withZone()方法详解及示例

> 原文：[https://www.geeksforgeeks.org/java-clock-withzone-method-in-java-with-examples/](https://www.geeksforgeeks.org/java-clock-withzone-method-in-java-with-examples/)

`Clock.withZone(ZoneId zone)`方法是`Clock`类的一个方法，它返回应用了该方法的时钟对象的一个不同时区的时钟副本。如果有一个时钟，需要更改时钟的区域，但不需要更改其他属性，则使用`withZone()`方法。此方法将区域作为参数，该参数是需要更改的时区。它返回带有区域的时钟，与参数中传递的区域相同。

## 语法

```java
public abstract Clock withZone(ZoneId zone)
```

## 参数

该方法采用`ZoneId`类型的强制参数`zone`，其中需要更改时区。

## 返回值

此方法返回应用此方法的时钟对象的时钟副本，不同的时区作为参数传递。

## 示例

```java
//Clock with default zone
Clock clock1=Clock.systemUTC();
ZoneId zone = ZoneId.of("Asia/Calcutta");
Clock clock2 = clock1.withZone(zone);
System.out.println(clock2.toString());
```

输出：
```
SystemClock[Asia/Calcutta]
```

解释：
当使用`ZoneId` `"Asia/Calcutta"`为`Clock`对象`clock1`调用`withZone()`时，`withZone()`方法将返回一个`Zone`为`"Asia/Calcutta"`的`Clock`。

下面的程序说明了`java.time.Clock`类的`withZone()`方法：

### 程序 1

在`withZone()`的帮助下，创建一个与第一个时钟具有相似属性但`zoneId`等于`"Asia/Calcutta"`的时钟。

```java
// Java program to demonstrate
// withZone() method of Clock class

import java.time.*;

// create class
public class withZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // create a base Clock with systemUTC() method
        Clock baseclock = Clock.systemUTC();

        // get ZonedDateTime object from baseclock
        // clock instant to get date time
        ZonedDateTime baseTime = baseclock
                                     .instant()
                                     .atZone(baseclock.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of baseclock "
                           + baseTime.toString());

        // create ZoneId object with Zone Asia/Calcutta
        ZoneId zone = ZoneId.of("Asia/Calcutta");

        // apply withZone() to change zone from utc to Asia/Calcutta
        Clock clockWithOtherZone = baseclock.withZone(zone);

        // get ZonedDateTime object from clockWithOtherZone
        // clock instant to get date time
        ZonedDateTime calcuttaTime = clockWithOtherZone
                                         .instant()
                                         .atZone(clockWithOtherZone.getZone());

        // print details of ZonedDateTime
        System.out.println("ZonedDateTime of clockWithOtherZone "
                           + calcuttaTime.toString());
    }
}
```

输出：
```java
ZonedDateTime of baseclock 2018-08-24T08:09:17.354Z
ZonedDateTime of clockWithOtherZone 2018-08-24T13:39:17.539+05:30[Asia/Calcutta]
```

### 程序 2

使用`getZone()`为`withZone()`创建的时钟打印`zoneId`。

```java
// Java program to demonstrate
// withZone() method of Clock class

import java.time.*;

// create class
public class withZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {
        // create a base Clock with systemDefaultZone() method
        Clock baseclock = Clock.systemDefaultZone();

        // print details of ZonedDateTime
        System.out.println("baseclock Zone:"
                           + baseclock.getZone());

        // create ZoneId object with Zone Asia/Calcutta
        ZoneId zone = ZoneId.of("Asia/Calcutta");

        // apply withZone() to change zone
        // of baseclock to Asia/Calcutta
        Clock clockWithOtherZone = baseclock.withZone(zone);

        // print details of ZonedDateTime
        System.out.println("clockWithOtherZone Zone:"
                           + clockWithOtherZone.getZone());
    }
}
```

输出：
```java
baseclock Zone:Etc/UTC
clockWithOtherZone Zone:Asia/Calcutta
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#withZone-java.time.ZoneId-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#withZone-java.time.ZoneId-)