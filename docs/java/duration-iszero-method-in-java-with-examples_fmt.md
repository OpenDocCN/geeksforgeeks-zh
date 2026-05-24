# Duration.isZero()方法在Java中的示例

> 原文：[https://www.geeksforgeeks.org/duration-iszero-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-iszero-method-in-java-with-examples/)

`java.time`包中`Duration`类的`isZero()`方法用于检查该时长是否为0长度。它返回一个描述相同内容的布尔值。

## 语法

```java
public boolean isZero()
```

## 参数

该方法不接受任何参数。

## 返回值

该方法返回一个`boolean`值。如果长度为0，则返回`true`。否则返回`false`。

以下示例说明了`Duration.isZero()`方法：

## 例1

```java
// Java code to illustrate isZero() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isZero() method
        boolean isZero = duration.isZero();

        System.out.println(isZero);
    }
}
```

## 输出

```java
false
```

## 例2

```java
// Java code to illustrate isZero() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P0DT0H0M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isZero() method
        boolean isZero = duration.isZero();

        System.out.println(isZero);
    }
}
```

## 输出

```java
true
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#isZero--](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#isZero--)