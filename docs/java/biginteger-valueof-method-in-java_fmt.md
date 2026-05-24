# Java 中的 BigInteger valueOf()方法

> 原文：[`https://www.geeksforgeeks.org/biginteger-valueof-method-in-java/`](https://www.geeksforgeeks.org/biginteger-valueof-method-in-java/)

`java.math.BigInteger.valueOf(long val)`方法返回一个`BigInteger`，其值等于作为参数传递的`long`的值。这个方法是静态方法，所以不需要创建`BigInteger`类的对象来调用这个函数，我们可以通过`BigInteger.valueOf(long val)`代码来调用。

## 语法：

```java
public static BigInteger valueOf(long val)
```

## 参数：
该方法接受单个参数`val`，即要创建的大整数的值。

## 返回值：
该方法返回`BigInteger`，其值等于作为参数传递的`long`值。

下面的程序说明了`BigInteger`类的`valueOf(long val)`方法：

## 示例 1：
在不创建`BigInteger`对象的情况下应用`valueOf()`。

```java
// Java program to demonstrate valueOf() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        // apply valueOf()
        b1 = BigInteger.valueOf(456782765);
        b2 = BigInteger.valueOf(12345543);

        // print result
        System.out.println("Value of BigInteger b1: " + b1);
        System.out.println("Value of BigInteger b2: " + b2);
    }
}
```

## 输出：

```java
Value of BigInteger b1: 456782765
Value of BigInteger b2: 12345543
```

## 示例 2：
通过创建`BigInteger`对象来应用`valueOf()`。

```java
// Java program to demonstrate valueOf() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger objects
        BigInteger b1, b2, b3;

        // create bigInteger with some value
        b1 = new BigInteger("532721");

        // apply valueOf()
        b2 = b1.valueOf(234567898);
        b3 = b2.valueOf(98765432);

        // print result
        System.out.println("Value of BigInteger 1: " + b2);
        System.out.println("Value of BigInteger 2: " + b3);
    }
}
```

## 输出：

```java
Value of BigInteger 1: 234567898
Value of BigInteger 2: 98765432
```

## 参考：
[`https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#valueOf(long)`](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#valueOf(long))