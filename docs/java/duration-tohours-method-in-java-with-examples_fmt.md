# Java 中的 Duration toHours() 方法，示例

> 原文：[`https://www.geeksforgeeks.org/duration-tohours-method-in-java-with-examples/`](https://www.geeksforgeeks.org/duration-tohours-method-in-java-with-examples/)

使用 `java.time` 包中 `Duration` 类的 `toHours()` 方法获取该持续时间的小时数值。

## 语法

```java
public long toHours()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个 `long` 值，即该时长内的小时数。

以下示例说明了 `Duration.toHours()` 方法：

## 例 1

```java
// Java code to illustrate toHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of hours
        // using toHours() method
        System.out.println(duration.toHours());
    }
}
```

**输出：**

```java
Duration: PT51H4M
```

## 例 2

```java
// Java code to illustrate toHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of hours
        // using toHours() method
        System.out.println(duration.toHours());
    }
}
```

**输出：**

```java
Duration: PT10H
```

## 参考

[`https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toHours--`](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toHours--)