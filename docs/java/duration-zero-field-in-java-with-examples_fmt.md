# Java 中的持续时间零字段，示例

> 原文：[`https://www.geeksforgeeks.org/duration-zero-field-in-java-with-examples/`](https://www.geeksforgeeks.org/duration-zero-field-in-java-with-examples/)

`java.time`包中`Duration`类的`ZERO`字段用于将该持续时间值设置为零。它类似于 Java 中其他数据类型的空值。

## 语法：

```java
Duration duration = Duration.ZERO;
```

以下示例说明了`Duration.ZERO`字段：

## 例 1：

```java
// Java code to illustrate ZERO field

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() field
        Duration duration
            = Duration.parse("P2DT3H4M");

        // Display the duration
        System.out.println(duration);

        // Now set the duration to ZERO
        duration = Duration.ZERO;

        // Display the duration
        System.out.println(duration);
    }
}
```

**Output:**

```java
PT51H4M
PT0S
```

## 例 2：

```java
// Java code to illustrate ZERO field

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration
            = Duration.ofDays(-5);

        // Display the duration
        System.out.println(duration);

        // Now set the duration to ZERO
        duration = Duration.ZERO;

        // Display the duration
        System.out.println(duration);
    }
}
```

**输出:**

```java
PT-120H
PT0S
```

**参考:** [`https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ZERO`](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ZERO)