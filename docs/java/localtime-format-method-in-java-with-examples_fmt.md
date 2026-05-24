# LocalTime.format() 方法详解（带示例）

> 原文：[https://www.geeksforgeeks.org/localtime-format-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-format-method-in-java-with-examples/)

`LocalTime` 类的 `format()` 方法用于使用作为参数传递的指定格式化程序格式化该时间。此方法基于传递给字符串的格式化程序来格式化此时间。

## 语法

```java
public String format(DateTimeFormatter formatter)
```

## 参数
该方法接受单个参数 `formatter`，它是指定的格式化程序。它不应为 `null`。

## 返回值
该方法返回格式的时间字符串。

## 异常
如果打印过程中出现错误，该方法将抛出 `DateTimeException`。

下面的程序说明了 `format()` 方法：

## 示例 1

```java
// Java program to demonstrate
// LocalTime.format() method

import java.time.*;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time
            = LocalTime.parse("03:18:23");

        // create formatter Object
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_TIME;

        // apply format
        String value = time.format(formatter);

        // print result
        System.out.println("value : "
                           + value);
    }
}
```

**输出：**

```java
value : 03:18:23
```

## 示例 2

```java
// Java program to demonstrate
// LocalTime.format() method

import java.time.*;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time
            = LocalTime.parse("23:59:59");

        // create formatter Object for ISO_LOCAL_TIME
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_LOCAL_TIME;

        // apply format
        String value = time.format(formatter);

        // print result
        System.out.println("value : "
                           + value);
    }
}
```

**输出：**

```java
value : 23:59:59
```

## 参考
[https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#format(java.time.format.DateTimeFormatter)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#format(java.time.format.DateTimeFormatter))