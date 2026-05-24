# Java 中的 Instant toString()方法，示例

> 原文：[https://www.geeksforgeeks.org/instant-tostring-method-in-java-with-examples/](https://www.geeksforgeeks.org/instant-tostring-method-in-java-with-examples/)

`Instant`类的`toString()`方法使用 ISO-8601 表示返回该时刻的字符串表示，使用的格式与`DateTimeFormatter.ISO_INSTANT`相同。

## 语法

```java
public String toString()
```

## 返回

这个方法返回这个瞬间的 ISO-8601 表示，不为空。

下面的程序说明了`toString()`方法：

## 程序 1

```java
// Java program to demonstrate
// Instant.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-28T19:34:50.63Z");

        // print Instant using toString()
        System.out.println("Instant: "
                           + instant.toString());

        // addition of 84000 seconds to this instant
        Instant returnedValue
            = instant.plusSeconds(84000);

        // print result Instant using toString()
        System.out.println("Returned Instant: "
                           + returnedValue.toString());
    }
}
```

## 程序 2

```java
// Java program to demonstrate
// Instant.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2022-06-21T19:34:50.63Z");

        // print Instant using toString()
        System.out.println("Instant: "
                           + instant);
    }
}
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#toString()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#toString())