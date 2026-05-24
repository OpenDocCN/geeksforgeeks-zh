# Java 中的 Duration plusHours(long)方法，示例

> 原文: [https://www.geeksforgeeks.org/duration-plushourslong-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-plushourslong-method-in-java-with-examples/)

`java.time`包中`Duration`类的`plusHours(long)`方法用于获取该持续时间的不可变副本，并添加指定的小时数，作为参数传递。

## 语法

```java
public Duration plusHours(long numberOfHours)
```

## 参数

该方法接受一个参数`numberOfHours`，即需要增加的小时数。它可以是正数或负数，但不能为空。

## 返回值

该方法返回一个`Duration`，它是一个不可变的现有持续时间的副本，其中添加了参数小时数。

## 异常

如果出现数值溢出，这个方法抛出`ArithmeticException`。

## 示例

以下示例说明了`Duration.plusHours()`方法:

### 例 1

```java
// Java code to illustrate plusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration added
        // using plusHours() method
        System.out.println(duration1.plusHours(2));
    }
}
```

**输出:**

```
PT53H4M
```

### 例 2

```java
// Java code to illustrate plusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration added
        // using plusHours() method
        System.out.println(duration1.plusHours(5));
    }
}
```

**输出:**

```
PT5H4M
```

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusHours-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#plusHours-long-)