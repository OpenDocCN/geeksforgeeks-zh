# Java 中的分钟(长)持续时间方法，示例

> 原文：[https://www.geeksforgeeks.org/duration-ofminuteslong-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-ofminuteslong-method-in-java-with-examples/)

`java.time`包中`Duration`类的`ofMinutes()`方法用于获取 1 分钟格式的时长。在这种方法中，秒以 1 分钟格式的总秒计算，即每分钟 60 秒。

## 语法

```java
public static Duration ofMinutes(long minutes)
```

## 参数

该方法接受一个参数`minutes`，即分钟数。它可以是积极的，也可以是消极的。

## 返回值

该方法返回一个`Duration`，以 1 分钟的格式表示时间。

## 异常

如果输入分钟数超过持续时间的容量，该方法抛出`ArithmeticException`。

以下示例说明了`Duration.ofMinutes()`方法：

## 例 1

```java
// Java code to illustrate ofMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Minutes
        long noOfMinutes = 5;

        // Duration using ofMinutes() method
        Duration duration
            = Duration.ofMinutes(noOfMinutes);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

## 例 2

```java
// Java code to illustrate ofMinutes() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Minutes
        long noOfMinutes = -214545;

        // Duration using ofMinutes() method
        Duration duration
            = Duration.ofMinutes(noOfMinutes);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofMinutes-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofMinutes-long-)