# Java 中的 LocalTime withNano() 方法示例

> 原文：[`https://www.geeksforgeeks.org/localtime-withnano-method-in-java-with-examples/`](https://www.geeksforgeeks.org/localtime-withnano-method-in-java-with-examples/)

`LocalTime` 类的 `withNano()` 方法用于获取这个 `LocalTime` 的副本，其中纳秒（Nano）被更改为作为参数传递给该方法的值。该本地时间的其余部分将保持不变。此实例是不可变的，不受此方法调用的影响。

## 语法

```java
public LocalTime withNano(int nano)
```

## 参数

该方法接受单个参数 `nano`，表示要在结果中设置的纳秒值，范围从 0 到 999,999,999。

## 返回值

此方法返回一个基于此时间与请求的纳秒值的 `LocalTime` 实例。

## 异常

如果纳秒值无效，该方法将抛出 `DateTimeException`。

## 示例

以下程序说明了 `withNano()` 方法：

### 程序 1

```java
// Java program to demonstrate
// LocalTime.withNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print time
        System.out.println("Old LocalTime: "
                           + time);

        // Get a new LocalDateTime with nanos 100000
        LocalTime newtime = time.withNano(100000);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出：**

```java
Old LocalTime: 19:34:50.630
New LocalDateTime: 19:34:50.000100
```

### 程序 2

```java
// Java program to demonstrate
// LocalTime.withNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:21:30.13");

        // print time
        System.out.println("Old LocalTime: "
                           + time);

        // Get a new LocalDateTime with nanos 999999
        LocalTime newtime = time.withNano(999999);

        // print result
        System.out.println("New LocalDateTime: "
                           + newtime);
    }
}
```

**输出：**

```java
Old LocalTime: 01:21:30.130
New LocalDateTime: 01:21:30.000999999
```

## 参考文献

[`https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withNano(int)`](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#withNano(int))