# java 中的 java.time.Clock 类

> 原文: [https://www.geeksforgeeks.org/java-time-clock-class-in-java/](https://www.geeksforgeeks.org/java-time-clock-class-in-java/)

Java 时钟类存在于 `java.time` 包中。它是在 Java 8 中引入的，使用时区提供对当前即时、日期和时间的访问。

时钟类的使用不是强制性的，因为所有日期时间类都有一个 `now()` 方法，该方法使用默认时区的系统时钟。使用时钟类的主要目的是在任何需要的地方插入备用时钟。应用程序使用对象而不是静态方法来获取当前时间。这使得测试变得容易。我们可以将时钟作为参数传递给需要当前时刻的方法。

**声明:**

```java
public abstract class Clock extends Object
```

它是一个抽象类，所以我们不能实例化它，但是我们可以使用几个 `静态` 方法来访问它的实例。

**`systemUTC()` 方法:**

```java
public static Clock systemUTC()
```

此方法返回世界协调时时区中当前时刻的时钟实例。当你需要一个没有日期和时间的当前时刻时，这是最好的。

### 示例代码

```java
// Java program for creating instance of Clock
import java.time.Clock;

public class GFG {

    // main method
    public static void main(String[] args) {

        // creating a Clock instance using
        // systemUTC() method of Clock class
        Clock clock = Clock.systemUTC();

        // getting the current instant defined by clock
        System.out.println("UTC time = " + clock.instant());
    }
}
```

**输出**

```java
UTC time = 2021-02-07T16:16:43.863267Z
```

**`systemDefaultZone()` 方法**

```java
public static Clock systemDefaultZone()
```

此方法使用系统的默认时区返回当前时刻的时钟实例。

### 示例代码

```java
// Java program for creating instance of Clock
import java.time.Clock;

public class GFG {

    // main method
    public static void main(String[] args) {

        // creating a Clock instance using
        // systemDefaultZone() method of Clock class
        Clock clock = Clock.systemDefaultZone();

        // it will print "SystemClock[Asia/Calcutta]" for me.
        // The output may be different because of server
        // system clock.
        System.out.println(clock);

        // printing zone of clock instance
        // it will print "Time zone : Asia/Calcutta" for me.
        System.out.println("Time Zone : " + clock.getZone());
    }
}
```

**输出**

```java
SystemClock[Etc/UTC]
Time Zone : Etc/UTC
```

### 方法

| 方法 | 描述 |
| --- | --- |
| `fixed(Instant fixed, ZoneId zone)` | 用于获取总是返回相同时刻的时钟。 |
| `getZone()` | 返回给定时钟的时区。 |
| `instant()` | 用于获取时钟的当前时刻。 |
| `millis()` | 返回时钟的当前毫秒瞬间。 |
| `offset(Clock baseClock, Duration offsetDuration)` | 返回一个时钟，该时钟从添加了指定持续时间的指定时钟返回瞬间。 |
| `system(ZoneId zone)` | 返回指定区域标识的当前时刻的时钟对象。 |
| `systemDefaultZone()` | 使用系统的默认时区返回当前时刻的时钟实例。 |
| `systemUTC()` | 返回以世界协调时时区表示的当前时刻的时钟实例。 |
| `tick(Clock baseClock, Duration tickDuration)` | 返回从指定基准时钟截断到指定持续时间最近的时刻。 |
| `tickMinutes(ZoneId zone)` | 返回给定时区当前整点钟的时钟对象。 |
| `tickSeconds(ZoneId zone)` | 返回给定时区内当前时刻的时钟对象，单位为整秒。 |
| `withZone(ZoneId zone)` | 创建一个不同时区的时钟副本。 |