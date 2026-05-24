# Java 中 `Duration.from(TemporalUnit)` 方法示例

> 原文：[https://www.geeksforgeeks.org/duration-fromtemporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-fromtemporalunit-method-in-java-with-examples/)

`java.time` 包中的 `Duration` 类的 `from(TemporalUnit)` 方法用于从作为 `TemporalUnit` 中第一个参数传递的金额中获取持续时间。时间单位可以是天、小时等。

## 语法

```java
public static Duration from(TemporalUnit amount)
```

## 参数

该方法接受一个参数 `amount`，该量是要从中找到持续时间的量，作为时间单位传递。

## 返回值

该方法返回一个表示指定金额时间的 `Duration`。

## 异常

此方法抛出以下异常：

*   `ArithmeticException`：如果发生数值溢出。
*   `DateTimeException`：如果无法将其转换为持续时间。

以下示例说明了 `Duration.from()` 方法：

### 例 1

```java
// Java code to illustrate from() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount
        Duration duration = Duration.ofDays(5);

        // Duration using from() method
        Duration duration1 = Duration.from(duration);

        System.out.println(duration1.getSeconds());
    }
}
```

**输出：**

```java

```

### 例 2

```java
// Java code to illustrate from() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the amount
        Duration duration = Duration.ofHours(5);

        // Duration using from() method
        Duration duration1 = Duration.from(duration);

        System.out.println(duration1.getSeconds());
    }
}
```

**输出：**

```java

```

## 参考

[Oracle 文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#from-java.time.temporal.TemporalAmount-)