# Java 中 `LocalTime` `toSecondOfDay()` 方法示例

> 原文：[https://www.geeksforgeeks.org/localtime-tosecondofday-method-in-java-with-examples/](https://www.geeksforgeeks.org/localtime-tosecondofday-method-in-java-with-examples/)

`LocalTime` 类的 `toSecondOfDay()` 方法用于从该 `LocalTime` 以秒为单位返回时间。此方法返回的值介于 0 到 `24 * 60 * 60 - 1` 之间。

## 语法

```java
public int toSecondOfDay()
```

## 参数

该方法不接受参数。

## 返回值

这个方法返回一个 `int` 值，它是一天中的秒数，相当于这个时间。

## 示例程序

下面的程序说明了 `toSecondOfDay()` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalTime.toSecondOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // extract second of day from toSecondOfDay()
        int value = time.toSecondOfDay();

        // print result
        System.out.println("Second of day: "
                           + value);
    }
}
```

**输出：**

```java
Second of day: 70490
```

### 程序 2

```java
// Java program to demonstrate
// LocalTime.toSecondOfDay() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:21:45.98");

        // extract Second of day from toSecondOfDay()
        int value = time.toSecondOfDay();

        // print result
        System.out.println("Second of day: "
                           + value);
    }
}
```

**输出：**

```java
Second of day: 84105
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#toSecondOfDay()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#toSecondOfDay())