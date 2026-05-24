# Java 中的 `Instant.plusSeconds()` 方法示例

> 原文：[https://www.geeksforgeeks.org/instant-plusseconds-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-plusseconds-method-in-java-with-examples/)

`Instant` 类的 `plusSeconds()` 方法将作为参数传递的秒值添加到该瞬间，并将结果作为即时对象返回。这个返回的即时消息是不可变的。

## 语法

```java
public Instant plusSeconds(long secondsToAdd)
```

## 参数

该方法接受一个参数 `secondsToAdd`，即秒添加。

## 返回值

此方法在加上秒后返回 `Instant`。

## 异常

如果结果超过最大或最小瞬间，该方法抛出以下异常：

*   `DateTimeException`。
*   `ArithmeticException`：如果存在数值溢出。

下面的程序说明了 `plusSeconds()` 方法：

## 程序 1

```java
// Java program to demonstrate
// Instant.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant
        System.out.println("Instant: "
                           + instant);

        // addition of 84000 seconds to this instant
        Instant returnedValue
            = instant.plusSeconds(84000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

## 输出

```java
Instant: 2018-10-28T19:34:50.630Z
Returned Instant: 2018-10-29T18:54:50.630Z
```

## 程序 2

```java
// Java program to demonstrate
// Instant.plusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current instant: "
                           + instant);

        // addition of 930000 seconds
        // to this instant
        Instant returnedValue
            = instant.plusSeconds(930000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

## 输出

```java
Current instant: 2018-11-28T05:39:46.572Z
Returned Instant: 2018-12-08T23:59:46.572Z
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plusSeconds(long)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#plusSeconds(long))