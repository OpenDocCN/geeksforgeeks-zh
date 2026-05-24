# Java 中的 Clock.system() 方法，示例

> 原文：[https://www.geeksforgeeks.org/clock-system-method-in-java-with-examples/](https://www.geeksforgeeks.org/clock-system-method-in-java-with-examples/)

`Clock.system(ZoneId zone)` 方法是 `Clock` 类的静态方法，它返回一个时钟，该时钟使用最佳可用系统时钟返回当前瞬间，并将时钟的 `ZoneId` 设置为传递的 `ZoneId`。如果时钟可用，此方法可以使用 `System.currentTimeMillis()` 或其他更高分辨率的时钟。

在从 `Instant` 转换为日期或时间时，指定的时区用于给出该时区的日期和时间。从该方法返回的时钟是不可变的、线程安全的和可序列化的。

## 语法

```java
public static Clock system(ZoneId zone)
```

## 参数

该方法采用强制参数 `zone`，该区域是将 `Instant` 转换为日期时间时使用的时区。

## 返回

该方法返回给定 `ZoneId` 的 `Clock` 对象。

## 示例

```java
// create a Zone Id for Europe/Paris
ZoneId zoneId = ZoneId.of("Europe/Paris");

// base Clock with default zone
Clock realClock = Clock.system(zoneId);
System.out.println(clock.instant());
```

输出：
```
2018-08-21T10:25:52.361Z
```

解释：
当你为 `Clock` 调用 `system(ZoneId)` 时，该方法将为给定的 `ZoneId` 返回一个类对象。你可以通过使用类的 `Instant` 来获取时钟的日期和时间。

下面的程序说明了 `java.time.Clock` 类的 `system(ZoneId)` 方法：

### 程序 1

用 `system(ZoneId)` 创建时钟，其中 `ZoneId` 为 `"Europe/Paris"`，并打印时钟的日期和时间。

```java
// Java program to demonstrate
// system(ZoneId) method of Clock class

import java.time.*;

// create class
public class systemMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Europe/Paris
        ZoneId zoneId = ZoneId.of("Europe/Paris");

        // create Clock with system(zoneId) method
        Clock clock = Clock.system(zoneId);

        // get instant of class
        Instant instant = clock.instant();

        // get ZonedDateTime object from instantObj to get date time
        ZonedDateTime time = instant.atZone(clock.getZone());

        // print details of time
        System.out.println("Instant for class is " + time.toString());
    }
}
```

输出：

```java
Instant for class is 2018-08-22T13:53:35.779+02:00[Europe/Paris]
```

### 程序 2

使用 `system()` 创建带 `"US/Arizona"` 区域的时钟，并使用 `getZone()` 打印区域标识。

```java
// Java program to demonstrate
// system(ZoneId) method of Clock class

import java.time.*;

// create class
public class systemMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for US/Arizona
        ZoneId zoneId = ZoneId.of("US/Arizona");

        // create Clock with system(zoneId) method
        Clock clock = Clock.system(zoneId);

        // print details of ZoneId of new Clock
        System.out.println("ZoneID of class is "
                           + clock.getZone());
    }
}
```

输出：

```java
ZoneID of class is US/Arizona
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#system-java.time.ZoneId-](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#system-java.time.ZoneId-)