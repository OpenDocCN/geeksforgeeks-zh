# Java 中 Duration toMillis()方法，示例

> 原文：[`https://www.geeksforgeeks.org/duration-tomillis-method-in-java-with-examples/`](https://www.geeksforgeeks.org/duration-tomillis-method-in-java-with-examples/)

使用 `java.time` 包中 `Duration` 类的 `toMillis()` 方法获取该持续时间的值，单位为毫秒。

## 语法

```java
public long toMillis()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个 `long` 值，即该时长内的毫秒数。

以下示例说明了 `Duration.toMillis()` 方法：

## 例 1

```java
// Java code to illustrate toMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillis() method
        System.out.println(duration.toMillis());
    }
}
```

**输出：**

```java
Duration: PT51H4M
```

## 例 2

```java
// Java code to illustrate toMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofMillis() method
        Duration duration
            = Duration.ofMillis(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of milli-seconds
        // using toMillis() method
        System.out.println(duration.toMillis());
    }
}
```

**输出：**

```java
Duration: PT0.01S
```

**参考：** [`https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMillis--`](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toMillis--)