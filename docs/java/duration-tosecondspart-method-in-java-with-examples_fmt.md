# Java 中的 `Duration` `toSecondsPart()`方法，示例

> 原文：[https://www.geeksforgeks.org/duration-tosecondspart-method-in-java-with-examples/](https://www.geeksforgeks.org/duration-tosecondspart-method-in-java-with-examples/)

`java.time`包中`Duration`类的`toSecondsPart()`方法用于通过除以一分钟的秒数得到该持续时间的值。

## 语法：
```java
public long toSecondsPart()
```

## 参数：
该方法不接受任何参数。

## 返回值：
这个方法返回一个`long`值，这个长值是这个持续时间内的秒数除以一分钟的秒数。

以下示例说明了`Duration.toSecondsPart()`方法：

## 例 1：
```java
// Java code to illustrate toSecondsPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSecondsPart() method
        System.out.println(duration.toSecondsPart());
    }
}
```

## 输出：
```java
Duration: PT51H4M
```

## 例 2：
```java
// Java code to illustrate toSecondsPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSecondsPart() method
        System.out.println(duration.toSecondsPart());
    }
}
```

## 输出：
```java
Duration: PT10S
```

## 参考：
[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toSecondsPart--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toSecondsPart--)