# Java 中的 BigInteger modPow() 方法

> 原文：[https://www.geeksforgeeks.org/biginteger-modpow-method-in-java/](https://www.geeksforgeeks.org/biginteger-modpow-method-in-java/)

先决条件：[大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

方法返回一个 `BigInteger`，其值为 (`this`<sup>`exponent`</sup> mod `m`)。
如果 `exponent` == 1，返回值为 (`this` mod `m`)。如果 `exponent` < 0，返回值为 (`this`<sup>`-exponent`</sup> 的模乘逆。如果 `m` <= 0，该方法将引发 `ArithmeticException`。

**语法：**

```java
public BigInteger modPow(BigInteger exponent, BigInteger m)
```

**参数：** 该方法接受两个参数。

*   `exponent`：此参数指指数。
*   `m`：这个参数是指模量。

**返回值：** 该方法返回一个 `BigInteger` 对象，其值为 (`this`<sup>`exponent`</sup> mod `m`)。

**异常：**

*   `ArithmeticException`：如果 (`m` <= 0) 或指数为负，并且这个 `BigInteger` 相对于 `m` 不是素数。

**示例：**

```java
Input: biginteger1 = 23895 
       exponent = 15
       biginteger2 = 14189
Output: 344
Explanation:
result = biginteger1.modPow(exponent, biginteger2)
23895^15 % 14189 = 344

Input: biginteger1 = 6547890621
       exponent = 4532415
       biginteger2 = 76543278906
Output: 1039609179
Explanation:
6547890621^4532415 % 76543278906 = 1039609179
```

下面的程序说明了 `java.math.BigInteger.modPow()` 方法：

## 示例代码

```java
// Code to illustrate modpow() method of BigInteger
import java.math.*;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {

        // Create 3 BigInteger objects
        BigInteger biginteger1, biginteger2, result;

        // Initializing all BigInteger Objects
        biginteger1 = new BigInteger("23895");
        biginteger2 = new BigInteger("14189");
        BigInteger exponent = new BigInteger("15");

        // Perform modPow operation on the objects and exponent
        result = biginteger1.modPow(exponent, biginteger2);
        String expression = biginteger1 + "^" + exponent + " % "
                            + biginteger2 + " = " + result;

        // Displaying the result
        System.out.println(expression);
    }
}
```

**输出：**

```java
23895^15 % 14189 = 344
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#abs()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#abs())