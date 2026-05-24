# 持续时间 `toDaysPart()` 方法在 Java 中的示例

> 原文：[https://www.geeksforgeeks.org/duration-todayspart-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-todayspart-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `toDaysPart()` 方法是用秒数除以 86400 得到这个持续时间的值。

## 语法

```java
public long toDaysPart()
```

## 参数

该方法不接受任何参数。

## 返回值

这个方法返回一个 `long` 值，这个长值是这个持续时间内的天数除以 86400。

以下示例说明了 `Duration.toDaysPart()` 方法：

## 示例 1

```java
// Java code to illustrate toDaysPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDaysPart() method
        System.out.println(duration.toDaysPart());
    }
}
```

**输出：**

```java
Duration: PT51H4M
2
```

## 示例 2

```java
// Java code to illustrate toDaysPart() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofDays() method
        Duration duration
            = Duration.ofDays(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of days
        // using toDaysPart() method
        System.out.println(duration.toDaysPart());
    }
}
```

**输出：**

```java
Duration: PT240H
10
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toDaysPart--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toDaysPart--)