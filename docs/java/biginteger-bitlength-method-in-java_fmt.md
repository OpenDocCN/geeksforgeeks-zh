# Java 中的大整数 bitLength() 方法

> 原文：[https://www.geeksforgeeks.org/biginteger-bitlength-method-in-java/](https://www.geeksforgeeks.org/biginteger-bitlength-method-in-java/)

`Java.math.BigInteger.bitLength()` 方法返回此 `BigInteger` 的最小二进制补码表示中的位数，不包括符号位。对于正的大整数，这相当于普通二进制表示中的位数。位长法计算 `⌈log₂(this < 0 ? -this : this + 1)⌉`。

**语法：**

```java
public int bitLength()
```

**参数：** 该方法不返回任何参数。

**返回值：** 该方法用于返回这个大整数的最小二进制补码表示中的位数，不包括符号位。

**例：**

```java
Input: value = 2300 
Output: 12
Explanation:
Binary signed 2's complement of 2300 = 0000100011111100
first four bits are singed bit so exclude them then remaining 
no of bits = 12. So bitLength in 0000100011111100 = 12.

Input: value = 5482549
Output: 23
```

下面的程序说明了 `BigInteger` 的 `bitLength()` 方法的使用。

```java
// Program to demonstrate bitLength() method of BigInteger

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Create BigInteger objects
        BigInteger biginteger = new BigInteger("2300");

        // Call bitLength() method on bigInteger
        int count = biginteger.bitLength();

        String result = "bitLength of " + biginteger +
                        " is " + count;

        // Print result
        System.out.println(result);
    }
}
```

**输出：**

```java
bitLength of  2300 is 12
```

**参考：** [https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#bitLength()](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#bitLength())