# Java 中的 BigInteger mod() 方法

> 原文：[https://www.geeksforgeeks.org/biginteger-mod-method-in-java/](https://www.geeksforgeeks.org/biginteger-mod-method-in-java/)

`java.math.BigInteger.mod(BigInteger big)` 方法返回一个 `BigInteger`，其值等于（这个 `BigInteger` mod `big`（作为参数传递的 `BigInteger`））。换句话说，我们可以说这个方法在执行（this % big）步骤后返回值。mod 操作在这个大整数被作为参数传递的另一个大整数除之后找到余数。

`java.math.BigInteger.mod(BigInteger big)` 和 `java.math.BigInteger.remainder(BigInteger val)` 这两个函数都可以找到余数，但是 mod 操作总是返回一个非负的 `BigInteger`。

## 语法

```java
public BigInteger mod(BigInteger big)
```

## 参数

该函数接受单个强制参数 `big`，它指定了我们想要用来划分这个 `BigInteger` 对象的 `BigInteger` 对象。

## 返回值

该方法返回的 `BigInteger` 等于这个 `BigInteger` mod `big`（作为参数传递）。

## 异常

方法在 `big <= 0` 时抛出 `ArithmeticException`。

## 示例

```java
Input: BigInteger1=321456, BigInteger2=31711
Output: 4346
Explanation: BigInteger1.mod(BigInteger2)=4346. The divide operation between 
321456 and 31711 returns 4346 as remainder.

Input: BigInteger1=59185482345, BigInteger2=59185482345
Output: 0
Explanation: BigInteger1.mod(BigInteger2)=0. The divide operation between 
59185482345 and 59185482345 returns 0 as remainder.
```

下面的程序说明了 `BigInteger` 类的 `mod()` 方法：

### 例 1

```java
// Java program to demonstrate mod() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("31711");

        // apply mod() method
        BigInteger result = b1.mod(b2);

        // print result
        System.out.println("Result of mod "
                 + "operation between " + b1
                 + " and " + b2 +
                 " equal to " + result);
    }
}
```

**输出：**

```java
Result of mod operation between 321456 and 31711 equal to 4346
```

### 例 2：两者值相等时

```java
// Java program to demonstrate mod() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("3515219485");
        b2 = new BigInteger("3515219485");

        // apply mod() method
        BigInteger result = b1.mod(b2);

        // print result
        System.out.println("Result of mod "
                 + "operation between " + b1
                 + " and " + b2 +
                 " equal to " + result);
    }
}
```

**输出：**

```java
Result of mod operation between 3515219485 and 3515219485 equal to 0
```

### 例 3：当作为参数传递的 BigInteger 小于零时显示异常的程序

```java
// Java program to demonstrate mod() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("3515219485");
        b2 = new BigInteger("-1711");

        // apply mod() method
        BigInteger result = b1.mod(b2);

        // print result
        System.out.println("Result of mod "
                 + "operation between " + b1
                 + " and " + b2 +
                 " equal to " + result);
    }
}
```

**输出：**

```java
Exception in thread "main" java.lang.ArithmeticException: BigInteger: modulus not positive
    at java.math.BigInteger.mod(BigInteger.java:2458)
    at GFG.main(GFG.java:17)
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#mod(java.math.BigInteger)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#mod(java.math.BigInteger))