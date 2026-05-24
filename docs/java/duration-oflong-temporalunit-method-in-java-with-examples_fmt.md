# Java中Duration.of(long, TemporalUnit)方法详解

> 原文：[https://www.geeksforgeeks.org/duration-oflong-temporalunit-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-oflong-temporalunit-method-in-java-with-examples/)

`java.time`包中`Duration`类的`of(long, TemporalUnit)`方法用于获取作为第一个参数传递的金额在作为第二个参数传递的`TemporalUnit`中的持续时间。时间单位可以是天、小时等。

## 语法

```java
public static Duration of(long amount, TemporalUnit unit)
```

## 参数

此方法接受两个参数：

*   `amount`：即秒数。可以是正数或负数。
*   `unit`：指定的时间单位。

## 返回值

该方法返回一个以指定单位格式表示时间的`Duration`。

## 异常

此方法抛出以下异常：

*   `ArithmeticException`：如果输入的秒数超过了持续时间的容量。
*   `DateTimeException`：如果时间单位具有估计的持续时间。

以下示例说明了`Duration.of()`方法：

## 示例

### 示例1

```java
// Java code to illustrate of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // input amount of time
        long timeAmount = 5;

        // Duration using of() method
        Duration duration
            = Duration.of(timeAmount, ChronoUnit.DAYS);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

### 示例2

```java
// Java code to illustrate of() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // input amount of time
        long timeAmount = 5;

        // Duration using of() method
        Duration duration
            = Duration.of(timeAmount, ChronoUnit.HOURS);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#of-long-java.time.temporal.TemporalUnit-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#of-long-java.time.temporal.TemporalUnit-)