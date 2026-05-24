# Java 中的 `Duration.minusHours(long)` 方法示例

> 原文：[https://www.geeksforgeeks.org/duration-minushourslong-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-minushourslong-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `minusHours(long)` 方法用于获取该持续时间的不可变副本，减去指定的小时数，作为参数传递。

**语法：**

```java
public Duration minusHours(long numberOfHours)
```

**参数：** 该方法接受一个参数 `numberOfHours`，即需要减去的小时数。它可以是正数或负数，但不能为空。

**返回值：** 该方法返回 `Duration`，该持续时间是现有持续时间的不可变副本，并减去参数小时数。

**异常：** 如果出现数值溢出，该方法抛出 `ArithmeticException`。

以下示例说明 `Duration.minusHours()` 方法：

### 示例 1

```java
// Java code to illustrate minusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusHours() method
        System.out.println(duration1
                           .minusHours(2));
    }
}
```

**Output：**

```java
PT49H4M
```

### 示例 2

```java
// Java code to illustrate minusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusHours() method
        System.out.println(duration1
                           .minusHours(5));
    }
}
```

**Output：**

```java
PT-4H-56M
```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusHours-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#minusHours-long-)