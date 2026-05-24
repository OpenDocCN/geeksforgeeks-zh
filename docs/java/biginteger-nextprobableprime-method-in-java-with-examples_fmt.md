# Java 中的 BigInteger nextProbablePrime() 方法示例

> 原文：[https://www.geeksforgeeks.org/biginteger-nextprobableprime-method-in-java-with-examples/](https://www.geeksforgeeks.org/biginteger-nextprobableprime-method-in-java-with-examples/)

`nextProbablePrime()` 用于查找第一个可能是素数的大于这个 `BigInteger` 的整数。如果这个方法返回 `p`，那么在这个大整数和 `p` 之间（即对于任意整数 `q`，满足 `this < q < p`）没有质数 `q`，也就是说，它从不跳过任何大于用来调用这个方法的大整数的质数。

## 语法

```java
public BigInteger nextProbablePrime()
```

## 参数

该方法不接受任何参数。

## 返回值

这个方法返回一个 `BigInteger`，它是保存的第一个大于这个 `BigInteger` 的、可能是质数的整数。

## 异常

数值必须非负且不要太大，否则抛出 `ArithmeticException`。

## 示例

下面的程序说明了 `BigInteger` 类的 `nextProbablePrime()` 方法。

### 示例 1

```java
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // object of String created
        // Holds the value to find next prime number
        String input1 = "1516132";

        // Creating BigInteger object
        BigInteger a
            = new BigInteger(input1);

        // Using nextProbablePrime()
        result = a.nextProbablePrime();

        // Print result
        System.out.println("The next probable"
                           + " Prime number is "
                           + result);
    }
}
```

**输出：**

```java
The next probable Prime number is 1516153
```

### 示例 2：打印所有 100 以下的质数

```java
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // Creating BigInteger objects
        BigInteger a;

        // Printing all prime numbers
        // Below 100
        for (int i = 0; i < 100;) {
            a = new BigInteger(
                Integer.toString(i));

            // Using nextProbablePrime()
            result = a.nextProbablePrime();

            // Print the answer
            if (Integer.parseInt(
                    result.toString())
                < 100) {
                System.out.print(result + " ");
            }

            i = Integer.parseInt(
                result.toString());
        }
    }
}
```

**输出：**

```java
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97
```

### 示例 3：数值为负时显示异常的程序

```java
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // object of String created
        // Holds the value to find prime number
        String input1 = "-5";

        // Creating BigInteger objects
        BigInteger a
            = new BigInteger(input1);

        try {
            // Using nextProbablePrime()
            result = a.nextProbablePrime();
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.lang.ArithmeticException: start < 0: -5
```

要了解检查当前 `BigInteger` 是否是素数，请访问 [`isProbablePrime()` 方法](https://www.geeksforgeeks.org/biginteger-isprobableprime-method-in-java-with-examples/)页面。

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#nextProbablePrime()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#nextProbablePrime())