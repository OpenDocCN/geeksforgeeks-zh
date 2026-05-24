# Java 中的 `ChronoUnit.isDurationEstimated()` 方法示例

> 原文：[https://www.geeksforgeeks.org/chronounit-isdurationestimated-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronounit-isdurationestimated-method-in-java-with-examples/)

## 方法描述

`ChronoUnit` 枚举的 `isDurationEstimated()` 方法用于检查该计时单位的持续时间是否是一个估计值。该枚举中的所有时间单位（如 `NANOS`, `SECONDS`）都被认为是准确的，而所有日期单位（如 `DAYS`, `MONTHS`）都被认为是估计的。

## 语法

```java
public boolean isDurationEstimated()
```

## 参数

此方法不接受任何参数。

## 返回值

如果持续时间是估计的，此方法返回 `true`；如果是准确的，则返回 `false`。

## 示例程序

下面的程序说明了 `ChronoUnit.isDurationEstimated()` 方法的使用：

### 程序 1

```java
// Java program to demonstrate
// ChronoUnit.isDurationEstimated() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("NANOS");

        // apply isDurationEstimated()
        boolean isDurationEstimatedAttribute
            = chronoUnit.isDurationEstimated();

        // print
        System.out.println(
            "NANOS"
            + " is Duration Estimated attribute:"
            + isDurationEstimatedAttribute);
    }
}
```

**输出：**

```java
NANOS is Duration Estimated attribute:false
```

### 程序 2

```java
// Java program to demonstrate
// ChronoUnit.isDurationEstimated() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("DAYS");

        // apply isDurationEstimated()
        boolean isDurationEstimatedAttribute
            = chronoUnit.isDurationEstimated();

        // print
        System.out.println(
            "DAYS"
            + " is Duration Estimated attribute:"
            + isDurationEstimatedAttribute);
    }
}
```

**输出：**

```java
DAYS is Duration Estimated attribute:true
```

## 参考文献

[https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isDurationEstimated()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isDurationEstimated())