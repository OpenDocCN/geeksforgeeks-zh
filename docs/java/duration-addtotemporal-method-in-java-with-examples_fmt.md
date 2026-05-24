# Java 中的 Duration addTo(Temporal) 方法示例

> 原文: [https://www.geeksforgeeks.org/duration-addtotemporal-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-addtotemporal-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `addTo(Temporal)` 方法用于将该持续时间添加到指定的时态对象中，作为参数传递。

## 语法

```java
public Temporal addTo(Temporal temporalObject)
```

## 参数

此方法接受一个参数 `temporalObject`，即在此持续时间内需要调整的量。它不应为 `null`。

## 返回值

该方法返回一个相同类型的 `Temporal` 对象，并对其进行时间对象调整。

## 异常

此方法抛出：

*   `DateTimeException`：如果单位不是受支持的类型。
*   `ArithmeticException`：如果发生数值溢出。

以下示例说明了 `Duration.addTo()` 方法：

## 例 1

```java
// Java code to illustrate addTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        System.out.println("Original time: "
                           + currentTime);

        // Adjust the time
        // using addTo() method
        System.out.println(
            duration1
                .addTo(currentTime));
    }
}
```

## 输出

```java
Original time: 2018-11-26T07:01:13.535
2018-11-28T10:05:13.535
```

## 例 2

```java
// Java code to illustrate addTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration2
            = Duration.ofDays(-5);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        System.out.println("Original time: "
                           + currentTime);

        // Adjust the time
        // using addTo() method
        System.out.println(
            duration2
                .addTo(currentTime));
    }
}
```

## 输出

```java
Original time: 2018-11-26T07:01:16.615
2018-11-21T07:01:16.615
```

## 参考

[Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#addTo-java.time.temporal.Temporal-)