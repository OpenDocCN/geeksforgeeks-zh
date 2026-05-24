# Java 中 Duration.between() 方法之间的持续时间示例

> 原文：[https://www.geeksforgeeks.org/duration-betweentemporal-temporal-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-betweentemporal-temporal-method-in-java-with-examples/)

`java.time` 包中 `Duration` 类的 `between()` 方法用于获取作为参数传递的两个 `Temporal` 对象之间的持续时间。第一个参数包含在内，而第二个参数不包含在计算中。如果对象的类型不同，则持续时间将根据第一个对象的类型计算。

## 语法

```java
public static Duration between(Temporal startDuration, Temporal endDuration)
```

## 参数

该方法接受两个参数：

*   **Start duration**：即要计算的起始时刻。它包含在计算中。它不应为空。
*   **End duration**：即要计算的结束时刻。它在计算中是唯一的。它不应为空。

## 返回值

该方法返回一个 `Duration`，代表作为参数传递的时刻之间经过的时间。

## 异常

此方法抛出：

*   **Abnormal date and time**：如果无法获取时间间隔中的秒数。
*   **Arithmetic exception**：如果计算超出了 `Duration` 的容量。

以下示例说明了 `Duration.between()` 方法：

### 例 1

```java
// Java code to illustrate between() method
import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // Duration using between() method
        Duration duration
            = Duration.between(LocalTime.MIDNIGHT,
                               LocalTime.NOON);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

### 例 2

```java
// Java code to illustrate between() method
import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // Duration using between() method
        Duration duration
            = Duration.between(LocalTime.NOON,
                               LocalTime.MAX);

        System.out.println(duration.getSeconds());
    }
}
```

**输出：**

```java

```

## 参考

[甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#between-java.time.temporal.Temporal-java.time.temporal.Temporal-)