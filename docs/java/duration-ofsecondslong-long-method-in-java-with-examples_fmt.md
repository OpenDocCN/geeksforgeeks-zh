# Java 中 `ofSeconds(long, long)` 方法的持续时间举例

> 原文：[https://www.geeksforgeks.org/duration-ofsecondslong-long-method-in-java-with-examples/](https://www.geeksforgeks.org/duration-ofsecondslong-long-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `ofSeconds(long, long)` 方法用于获取 1 秒格式的时长。在这种方法中，秒以 1 秒的格式（即每秒 1 秒）计算为总秒。第二个参数 `nanoAdjustment` 用于以纳秒为单位调整秒。

## 语法

```java
public static Duration ofSeconds(long seconds, long nanoAdjustment)
```

## 参数

这个方法接受两个参数：

*   `seconds`：即秒数。可以是正数或负数。
*   `nanoAdjustment`：要对秒进行的纳秒调整。

## 返回值

该方法返回一个 `Duration`，以 1 秒的格式表示时间。

## 异常

如果输入秒数超过持续时间的容量，该方法抛出 `ArithmeticException`。

## 示例

以下示例说明了 `Duration.ofSeconds()` 方法：

### 例 1

```java
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = 214545;

        // input nanoSeconds adjustment to be made
        long nanoSecAdjust = 10000;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);
        Duration duration1
            = Duration.ofSeconds(noOfSeconds,
                                 nanoSecAdjust);

        System.out.println("Duration without adjustment: "
                           + duration.getSeconds());
        System.out.println("Duration with adjustment: "
                           + duration1.getSeconds());
    }
}
```

**输出：**

```java
Duration without adjustment: 214545
Duration with adjustment: 214545
```

### 例 2

```java
// Java code to illustrate ofSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Seconds
        long noOfSeconds = 214545;

        // input nanoSeconds adjustment to be made
        long nanoSecAdjust = -10000;

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(noOfSeconds);
        Duration duration1
            = Duration.ofSeconds(noOfSeconds,
                                 nanoSecAdjust);

        System.out.println("Duration without adjustment: "
                           + duration.getSeconds());
        System.out.println("Duration with adjustment: "
                           + duration1.getSeconds());
    }
}
```

**输出：**

```java
Duration without adjustment: 214545
Duration with adjustment: 214544
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofSeconds-long-long-)