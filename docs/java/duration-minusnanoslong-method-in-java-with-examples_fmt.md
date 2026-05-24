# Java 中 Duration.minusNanos(long) 方法示例

> 原文：[https://www.geeksforgeeks.org/duration-minusnanoslong-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-minusnanoslong-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `minusNanos(long)` 方法用于获取该持续时间的不可变副本，减去指定的纳秒数（作为参数传递）。

**语法：**

```java
public Duration minusNanos(long numberOfNanos)
```

**参数：** 该方法接受一个参数 `numberOfNanos`，即要减去的纳秒数。它可以是正数或负数，但不能为空。
**返回值：** 该方法返回一个 `Duration`，该持续时间是现有持续时间的一个不可变的副本，其中减去了参数指定的纳秒数。
**异常：** 如果出现数值溢出，该方法抛出 `ArithmeticException`。

以下示例说明了 `Duration.minusNanos()` 方法：

### 示例 1

```java
// Java code to illustrate minusNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusNanos() method
        System.out.println(duration1.minusNanos(2));
    }
}
```

**Output：**

```java
PT51H3M59.999999998S
```

### 示例 2

```java
// Java code to illustrate minusNanos() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusNanos() method
        System.out.println(duration1.minusNanos(5));
    }
}
```

**Output：**

```java
PT3M59.999999995S
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusNanos-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusNanos-long-)