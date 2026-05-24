# Java 中的持续天数(长)方法，示例

> 原文: [https://www.geeksforgeeks.org/duration-minusdayslong-method-in-java-with-examples/](https://www.geeksforgeeks.org/duration-minusdayslong-method-in-java-with-examples/)

`java.time`包中`Duration`类的`minusDays(long)`方法用于获取该持续时间的不可变副本，减去指定的天数，作为参数传递。

**语法:**

```java
public Duration minusDays(long numberOfDays)
```

**参数:** 该方法接受一个参数`numberOfDays`，即要减去的天数。它可以是正数或负数，但不能为空。
**返回值:** 该方法返回`Duration`，该持续时间是现有持续时间的不可变副本，并减去参数天数。
**异常:** 如果出现数值溢出，该方法抛出`ArithmeticException`。

以下示例说明了`Duration.minusDays()`方法:

## 代码示例

```java
// Java code to illustrate minusDays() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusDays() method
        System.out.println(duration1.minusDays(2));
    }
}
```

**Output:**

```java
PT3H4M
```