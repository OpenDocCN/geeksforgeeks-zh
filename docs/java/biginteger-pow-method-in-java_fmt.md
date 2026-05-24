# Java 中的 BigInteger pow()方法

> 原文: [https://www.geeksforgeeks.org/biginteger-pow-method-in-java/](https://www.geeksforgeeks.org/biginteger-pow-method-in-java/)

`BigInteger pow(int exponent)`方法用于计算一个大整数，该大整数是作为指数传递的某个其他数字的幂，其值等于`(this) ^ exponent`。此方法对调用此方法的当前`BigInteger`执行操作，并将指数作为参数传递。

## 语法:
```java
public BigInteger pow(int exponent)
```

## 参数:
这个方法接受一个参数`exponent`，它是这个大整数应该被提升到的指数。

## 返回:
该方法返回一个等于`(this) ^ exponent`的大整数。

## 异常:
参数`exponent`必须为正数(`exponent >= 0`)，否则抛出`ArithmeticException`。

## 示例:
```java
Input: BigInteger1=321456, exponent=5
Output: 3432477361331488865859403776
Explanation: BigInteger1.pow(exponent)=3432477361331488865859403776.
321456^5=3432477361331488865859403776

Input: BigInteger1=45321, exponent=3
Output: 93089018611161
Explanation: BigInteger1.pow(exponent)=93089018611161.
321456^5=93089018611161
```

## 示例 1:
下面的程序举例说明`BigInteger`类的`pow()`方法。
```java
// Java program to demonstrate
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("321456");
        int exponent = 5;

        // apply pow() method
        BigInteger result = b1.pow(exponent);

        // print result
        System.out.println("Result of pow operation between BigInteger "
             + b1 + " and exponent " + exponent + " equal to " + result);
    }
}
```
**输出:**
> Result of pow operation between BigInteger 321456 and exponent 5 equal to 3432477361331488865859403776

## 示例 2:
```java
// Java program to demonstrate
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("12346");
        int exponent = 6;

        // apply pow() method
        BigInteger result = b1.pow(exponent);

        // print result
        System.out.println("Result of pow operation between BigInteger "
             + b1 + " and exponent " + exponent + " equal to " + result);
    }
}
```
**输出:**
> Result of pow operation between BigInteger 12346 and exponent 6 equal to 3432477361331488865859403776

## 示例 3:
当作为参数传递的指数小于零时显示异常的程序。
```java
// Java program to demonstrate
// pow() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("76543");
        int exponent = -17;

        try {
            // apply pow() method
            BigInteger result = b1.pow(exponent);

            // print result
            System.out.println("Result of pow operation between " + b1
                               + " and " + exponent + " equal to " + result);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```
**输出:**
> java.lang.ArithmeticException: Negative exponent

**参考:** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#pow(int)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#pow(int))