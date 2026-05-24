# Java 中的 BigInteger negate() 方法

> 原文: [https://www.geeksforgeeks.org/biginteger-negate-method-in-java/](https://www.geeksforgeeks.org/biginteger-negate-method-in-java/)

先决条件: [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

**方法返回一个值为 `- this` 的 `BigInteger`。方法将改变 `BigInteger` 的符号位。**

## 语法

```java
public BigInteger negate()
```

## 参数

该方法不接受任何参数。

## 返回值

方法返回 `- this` 的运算结果。

## 示例

```java
Input: value = 2300
Output: -2300
Explanation:
Binary signed 2's complement of 2300 = 0000100011111100
Signed bit is 0000
change sign bit to 1111
so negate of 0000100011111100 in signed 2's complement is 1111011100000100
Decimal value = -2300.

Input: value = 567689 
Output: -567689
```

下面的程序说明了 `BigInteger` 的 `negate()` 方法。

```java
/*
 * Program Demonstrate negate() method of BigInteger 
 */
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Create BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Call negate() method to find -this
        BigInteger finalvalue = biginteger.negate();
        String result = "Result of negate operation on " + 
                        biginteger + " is " + finalvalue;

        // Prints result
        System.out.println(result);
    }
}
```

## 输出

```java
Result of negate operation on 2300 is -2300
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#negate()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#negate())