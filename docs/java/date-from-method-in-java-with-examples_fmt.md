# Java 中的 Date from()方法，示例

> 原文：[https://www.geeksforgeeks.org/date-from-method-in-java-with-examples/](https://www.geeksforgeeks.org/date-from-method-in-java-with-examples/)

[`Date`](https://www.geeksforgeeks.org/date-class-java-examples/)类的`from(Instant inst)`方法返回一个从`Instant`对象获得的`Date`实例。

## 语法：

```java
public static Date from(Instant inst)
```

## 参数：
该方法取一个需要转换的`Instant`型参数`inst`。

## 返回值：
该方法返回一个`Date`，该`Date`表示时间线上与`Instant`瞬间相同的点。

## 异常：
*   `NullPointerException`：当该`Instant`为空时抛出。
*   `IllegalArgumentException`：当`Instant`太大而无法表示为`Date`时抛出。

下面的程序说明了`from()`方法在Java中的使用：

## 示例 1：

```java
// Java code to demonstrate
// from() method of Date class

import java.time.Instant;
import java.util.Date;

public class JavaDateDemo {
    public static void main(String args[])
    {
        // Creating Date Object
        Date dateOne = new Date();

        // Creating Instant object
        Instant inst = Instant.now();

        // Displaying the instant
        System.out.println(
            "Present: "
            + dateOne.from(inst));
    }
}
```

### Output：

```java
Present: Tue Mar 26 06:45:40 UTC 2019
```

## 示例 2：

```java
import java.util.Date;
import java.util.Calendar;
import java.time.Instant;

public class GfG {
    public static void main(String args[])
    {
        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 00);

        // Set Date
        c1.set(Calendar.DATE, 30);

        // Set Year
        c1.set(Calendar.YEAR, 2019);

        // Creating a date object
        // with specified time.
        Date dateOne = c1.getTime();

        Instant inst = dateOne.toInstant();

        System.out.println(
            "Date: " + dateOne.from(inst));
    }
}
```

### Output：

```java
Date: Wed Jan 30 06:45:43 UTC 2019
```

## 参考：
[https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#from-java.time.Instant-](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#from-java.time.Instant-)