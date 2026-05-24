# Java 中的 Duration toNanos() 方法示例

> 原文：[https://www.geeksforgeeks.org/duration-tonanos-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-tonanos-method-in-java-with-examples/)

使用 `java.time` 包中 `Duration` 类的 `toNanos()` 方法获取该持续时间的值，单位为纳秒。

## 语法

```java
public long toNanos()
```

## 参数

该方法不接受任何参数。

## 返回值

此方法返回一个 `long` 值，即此时长内的纳秒数。

以下示例说明了 `Duration.toNanos()` 方法：

## 示例 1

```java
// Java code to illustrate toNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of nano-seconds
        // using toNanos() method
        System.out.println(duration.toNanos());
    }
}
```

**输出：**

```java
Duration: PT51H4M
```

## 示例 2

```java
// Java code to illustrate toNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofNanos() method
        Duration duration
            = Duration.ofNanos(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of nano-seconds
        // using toNanos() method
        System.out.println(duration.toNanos());
    }
}
```

**输出：**

```java
Duration: PT0.00000001S
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toNanos--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toNanos--)