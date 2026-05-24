# Java 中 Duration.minusMillis(long) 方法示例

> 原文：[`https://www.geeksforgeeks.org/duration-minusmillislong-method-in-java-with-examples/`](https://www.geeksforgeeks.org/duration-minusmillislong-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `minusMillis()` 方法用于获取该持续时间的不可变副本，减去指定的毫秒数，作为参数传递。

**语法：**

```java
public Duration minusMillis(long numberOfMillis)
```

**参数：** 该方法接受一个参数 `numberOfMillis`，即需要减去的毫秒数。它可以是正数或负数，但不能为空。

**返回值：** 该方法返回一个 `Duration`，它是一个不可变的现有持续时间的副本，参数值为毫秒。

**异常：** 如果出现数值溢出，这个方法抛出 `ArithmeticException`。

以下示例说明了 `minusMillis()` 方法：

## 示例 1

```java
// Java code to illustrate minusMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusMillis() method
        System.out.println(duration1.minusMillis(2));
    }
}
```

**输出：**

```java
PT51H3M59.998S
```

## 示例 2

```java
// Java code to illustrate minusMillis() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusMillis() method
        System.out.println(duration1.minusMillis(5));
    }
}
```

**输出：**

```java
PT3M59.995S
```

**参考：** [`https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusMillis-long-`](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusMillis-long-)