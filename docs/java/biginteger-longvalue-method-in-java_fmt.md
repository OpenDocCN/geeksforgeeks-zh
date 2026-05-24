# Java 中的 `BigInteger.longValue()` 方法

> 原文：[https://www.geeksforgeeks.org/biginteger-longvalue-method-in-java/](https://www.geeksforgeeks.org/biginteger-longvalue-method-in-java/)

`java.math.BigInteger.longValue()` 方法将这个 `BigInteger` 转换成一个 `long` 值。如果这个函数返回的值太大，无法放入 `long` 值，那么它将只返回低阶的 64 位。这种转换有可能会丢失关于 `BigInteger` 值整体大小的信息。这个方法也可以返回符号相反的结果。

## 语法

```java
public long longValue()
```

## 返回值

该方法返回一个 `long` 值，代表这个大整数的长值。

## 示例

```java
Input: BigInteger1=3214558191
Output: 3214558191
Explanation: BigInteger1.longValue()=3214558191.

Input: BigInteger1=32145535361361525377
Output: -4747952786057577855
Explanation: BigInteger1.longValue()=-4747952786057577855. This BigInteger is too big for longValue so it is returning lower 64 bit.
```

### 例 1：基本用法

以下程序说明了 `BigInteger` 类的 `longValue()` 方法。

```java
// Java program to demonstrate longValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("3214553537");
        b2 = new BigInteger("76137217351");

        // apply longValue() method
        long longValueOfb1 = b1.longValue();
        long longValueOfb2 = b2.longValue();

        // print longValue
        System.out.println("longValue of "
                           + b1 + " : " + longValueOfb1);
        System.out.println("longValue of "
                           + b2 + " : " + longValueOfb2);
    }
}
```

**输出：**

```java
longValue of 3214553537 : 3214553537
longValue of 76137217351 : 76137217351
```

### 例 2：当返回值对于 `long` 类型太大时

```java
// Java program to demonstrate longValue() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145535361361525377");
        b2 = new BigInteger("7613721535372632367351");

        // apply longValue() method
        long longValueOfb1 = b1.longValue();
        long longValueOfb2 = b2.longValue();

        // print longValue
        System.out.println("longValue of "
                           + b1 + " : " + longValueOfb1);
        System.out.println("longValue of "
                           + b2 + " : " + longValueOfb2);
    }
}
```

**输出：**

```java
longValue of 32145535361361525377 : -4747952786057577855
longValue of 7613721535372632367351 : -4783767069412450057
```

## 参考

[`BigInteger.longValue()` 文档](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#longValue())