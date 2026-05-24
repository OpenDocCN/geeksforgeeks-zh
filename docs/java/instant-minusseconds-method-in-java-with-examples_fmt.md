# Java 中的 Instant.minusSeconds() 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-minusseconds-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-minusseconds-method-in-java-with-examples/)

`Instant` 类的 `minusSeconds()` 方法从该瞬间中减去指定的秒数，并将结果作为 `Instant` 对象返回。这个 `Instant` 是不可变的。

**语法：**

```java
public Instant minusSeconds(long secondsToSubtract)
```

**参数：** 该方法接受一个参数 `secondsToSubtract`，即要减去的秒数。
**返回值：** 此方法在减去秒数后返回一个 `Instant`。

**异常：** 该方法抛出以下异常：

*   `DateTimeException`：如果结果超过最大或最小瞬间。
*   `ArithmeticException`：如果出现数值溢出。

下面的程序说明了 `minusSeconds()` 方法：

## 示例程序 1

```java
// Java program to demonstrate
// Instant.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-30T09:05:55.13Z");

        // current Instant
        System.out.println("Initialize instant: "
                           + instant);

        // subtract 4300 seconds from this instant
        Instant returnedValue
            = instant.minusSeconds(4300);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出**

```java
Initialize instant: 2018-10-30T09:05:55.130Z
Returned Instant: 2018-10-30T07:54:15.130Z
```

## 示例程序 2

```java
// Java program to demonstrate
// Instant.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current instant: "
                           + instant);

        // subtract 54000 from this instant
        Instant returnedValue
            = instant.minusSeconds(54000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**输出：**

```java
Current instant: 2018-11-27T06:44:04.901Z
Returned Instant: 2018-11-26T15:44:04.901Z
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minusSeconds(long)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minusSeconds(long))