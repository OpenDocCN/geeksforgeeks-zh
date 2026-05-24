# Java 8 中 BigInteger.byteValueExact() 方法详解（带示例）

> 原文：[https://www.geeksforgeeks.org/java-8-biginteger-bytevalueexact-method-with-examples/](https://www.geeksforgeeks.org/java-8-biginteger-bytevalueexact-method-with-examples/)

## 简介

`byteValueExact()` 方法是在 Java 8 中引入到 `java.math.BigInteger` 类中的。这是一个内置方法，用于将 `BigInteger` 的值转换为一个 `byte`，并检查转换过程中是否有信息丢失。如果 `BigInteger` 的值大于 127 或小于 -128，该方法将抛出 `ArithmeticException`，因为该值超出了 `byte` 类型的表示范围。

## 语法

```java
public byte byteValueExact()
```

## 返回值

此方法返回此 `BigInteger` 对应的 `byte` 值。

## 异常

如果 `BigInteger` 的值大于 127 或小于 -128，该方法将抛出 `ArithmeticException`，因为该值超出了 `byte` 类型的范围。

## 示例

```java
Input: 122
Output: 122
Explanation: 122 is given as input which is bigInteger
and byte value of 122 is 122

Input: -46
Output: -46
Explanation: -46 is given as input which is bigInteger 
and byte value of -46 is -46

Input: 200
Output: ArithmeticException
Explanation: When 200 is tried to convert to Byte,
since 200 > 127 (greater than a Byte's range), 
therefore it throws an arithmetic exception.
```

下面的程序说明了 `BigInteger` 类的 `byteValueExact()` 方法：

### 程序 1：演示正数（<=127）

```java
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big;
        big = new BigInteger("122");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the byte value
        byte b1 = big.byteValueExact();

        // print byte value
        System.out.println("Byte converted value : "
                           + b1);
    }
}
```

**程序 1 的输出：**

```java
BigInteger value : 122
Byte converted value : 122
```

### 程序 2：演示负数（>= -128）

```java
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("-46");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the byte value
        byte b1 = big.byteValueExact();

        // print byte value
        System.out.println("Byte converted value : "
                           + b1);
    }
}
```

**程序 2 的输出：**

```java
BigInteger value : -46
Byte converted value : -46
```

### 程序 3：演示负数（< -128）的 `byteValueExact()` 方法（将抛出 `ArithmeticException`）

```java
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("-200");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the byte value
            byte b1 = big.byteValueExact();

            // print byte value
            System.out.println("Byte converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**程序 3 的输出：**

```java
BigInteger value : -200
Exception: java.lang.ArithmeticException: BigInteger out of byte range
```

### 程序 4：演示正数（> 127）的 `byteValueExact()` 方法（将抛出 `ArithmeticException`）

```java
// Java program to demonstrate byteValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("200");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the byte value
            byte b1 = big.byteValueExact();

            // print byte value
            System.out.println("Byte converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**程序 4 的输出：**

```java
BigInteger value : 200
Exception: java.lang.ArithmeticException: BigInteger out of byte range
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#byteValueExact--](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#byteValueExact--)