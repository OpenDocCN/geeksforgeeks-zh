# Java 8 | BigInteger.shortValueExact() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/java-8-biginteger-shortvalueexact-method-with-examples/](https://www.geeksforgeeks.org/java-8-biginteger-shortvalueexact-method-with-examples/)

`BigInteger.shortValueExact()` 在 Java 8 中引入。这是一个内置函数，它将 `BigInteger` 的值转换为一个 `short`，并检查丢失的信息。如果 `BigInteger` 的值大于 32,767 或小于 -32,768；该方法将抛出 `ArithmeticException`，因为大整数不适合 `short` 范围。

## 语法

```java
public short shortValueExact()
```

## 返回值

这个方法返回这个 `BigInteger` 的 `short` 值。

## 异常

如果 `BigInteger` 的值大于 32,767 或小于 -32,768，则该方法抛出 `ArithmeticException`；因为这个范围不适合 `short` 范围。

## 例

```java
Input: 15,564
Output: 15,564
Explanation: 15,564 is given as input which is BigInteger
and short value of 15,564 is 15,564

Input: -17,584
Output: -17,584
Explanation: -17,584 is given as input which is BigInteger 
and short value of -17,584 is -17,584

Input: 40000
Output: ArithmeticException
Explanation: When 40000 is tried to convert to short,
since 40000 > 32,767 (greater than a short's range), 
therefore it throws an arithmetic exception.
```

下面的程序说明了 `BigInteger` 类的 `shortValueExact()` 方法：

### 程序 1：演示正数 < 32,767

```java
// Java program to demonstrate shortValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big;
        big = new BigInteger("15564");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the short value
        short b1 = big.shortValueExact();

        // print short value
        System.out.println("short converted value : "
                           + b1);
    }
}
```

`shortValueExact()` 方法输出：

```java
BigInteger value : 15564
short converted value : 15564
```

### 程序 2：演示负数 > -32,768

```java
// Java program to demonstrate shortValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("-17584");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        // convert big to the short value
        short b1 = big.shortValueExact();

        // print short value
        System.out.println("short converted value : "
                           + b1);
    }
}
```

`shortValueExact()` 方法输出：

```java
BigInteger value : -17584
short converted value : -17584
```

### 程序 3：演示负数 < -32,768 的 shortValueExact() 方法。它会抛出算术异常

```java
// Java program to demonstrate shortValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("-40000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the short value
            short b1 = big.shortValueExact();

            // print short value
            System.out.println("short converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

输出：

```java
BigInteger value : -40000
Exception: java.lang.ArithmeticException: BigInteger out of short range
```

### 程序 4：演示正数 > 32,767 的 shortValueExact() 方法。它会抛出算术异常

```java
// Java program to demonstrate shortValueExact()
// method of BigInteger Class

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a BigInteger object
        BigInteger big = new BigInteger("40000");

        // print value of BigInteger
        System.out.println("BigInteger value : "
                           + big);

        try {
            // convert big to the short value
            short b1 = big.shortValueExact();

            // print short value
            System.out.println("short converted value : "
                               + b1);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

输出：

```java
BigInteger value : 40000
Exception: java.lang.ArithmeticException: BigInteger out of short range
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#shortValueExact--](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html#shortValueExact--)