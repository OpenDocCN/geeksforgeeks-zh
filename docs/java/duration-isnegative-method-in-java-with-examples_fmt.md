# Duration 类的 isNegative() 方法（Java 示例）

> 原文：[https://www.geeksforgeeks.org/duration-isnegative-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-isnegative-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `isNegative()` 方法用于检查该时长是否为负。它返回一个描述相同内容的布尔值。

## 语法

```java
public boolean isNegative()
```

## 参数
该方法不接受任何参数。

## 返回值
该方法返回一个布尔值。如果持续时间为负，则返回 `true`。否则返回 `false`。

以下示例说明了 `Duration.isNegative()` 方法：

## 示例 1

```java
// Java code to illustrate isNegative() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isNegative() method
        boolean isNegative = duration.isNegative();

        System.out.println(isNegative);
    }
}
```

**输出：**

```java
false
```

## 示例 2

```java
// Java code to illustrate isNegative() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "-P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isNegative() method
        boolean isNegative = duration.isNegative();

        System.out.println(isNegative);
    }
}
```

**输出：**

```java
true
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#isNegative--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#isNegative--)