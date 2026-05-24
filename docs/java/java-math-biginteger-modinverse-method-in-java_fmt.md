# Java中的`BigInteger.modInverse()`方法

> 原文：[https://www.geeksforgeeks.org/java-math-biginteger-modinverse-method-in-java/](https://www.geeksforgeeks.org/java-math-biginteger-modinverse-method-in-java/)

**先决条件：** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

`modInverse()`方法返回这个`BigInteger`模`m`的模乘逆，如果`m <= 0`或者这个`BigInteger`没有乘逆模`m`（即`gcd(this, m) != 1`）。

## 语法
```java
public BigInteger modInverse(BigInteger m)
```

## 参数
`m` – 模量。

## 返回值
此方法返回一个`BigInteger`对象，其值为`((this)^(-1) mod m)`。

## 异常
*   `ArithmeticException` – 如果`m <= 0`，或者此`BigInteger`在模`m`下没有乘法逆元（即此`BigInteger`与`m`不互质）。

下面的程序说明了`BigInteger.modInverse()`方法：

### 程序 1
```java
import java.math.*;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);

        // create 2 BigInteger objects
        BigInteger biginteger1, biginteger2, result;

        // Initialize all BigInteger Objects
        biginteger1 = new BigInteger("8");
        biginteger2 = new BigInteger("21");

        // perform modInverse operation on biginteger1 using biginteger2.
        result = biginteger1.modInverse(biginteger2);

        String expression = biginteger1 + " ^ -1 % "
                            + biginteger2 + " = " + result;

        // print result value
        System.out.println(expression);
    }
}
```
**输出：**
```java
8 ^ -1 % 21 = 8
```

### 程序 2
```java
import java.math.*;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);

        // create 2 BigInteger objects
        BigInteger biginteger1, biginteger2, result;

        // Initialize all BigInteger Objects
        biginteger1 = new BigInteger(88882);
        biginteger2 = new BigInteger(22224);

        // perform modInverse operation on biginteger1 using biginteger2.
        result = biginteger1.modInverse(biginteger2);

        String expression = biginteger1 + " ^ -1 % "
                            + biginteger2 + " = " + result;

        // print result value
        System.out.println(expression);
    }
}
```
**输出：**
```java
Exception in thread "main" java.lang.ArithmeticException: BigInteger not invertible.
    at java.math.MutableBigInteger.modInverse(Unknown Source)
    at java.math.MutableBigInteger.mutableModInverse(Unknown Source)
    at java.math.BigInteger.modInverse(Unknown Source)
    at BigInteger.GFG2.main(GFG2.java:23)
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#modInverse(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#modInverse(java.math.BigInteger))