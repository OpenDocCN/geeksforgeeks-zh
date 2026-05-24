# Java 中秒(长)的持续时间方法，示例

> 原文：[https://www.geeksforgeeks.org/duration-ofseconds-long-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-ofseconds-long-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `ofSeconds(long)` 方法用于获取 1 秒格式的时长。在这种方法中，秒以 1 秒的格式（即每秒 1 秒）计算为总秒。

## 语法

```java
public static Duration ofSeconds(long seconds)
```

## 参数

该方法接受一个参数 `seconds`，即秒数。它可以是积极的，也可以是消极的。

## 返回值

该方法返回一个 `Duration`，以 1 秒的格式表示时间。

## 异常

如果输入秒数超过持续时间的容量，该方法抛出 `ArithmeticException`。

以下示例说明了 `Duration.ofSeconds()` 方法：

## 例 1

```java
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = 5;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

## 例 2

```java
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = -214545;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

**参考：**[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-)