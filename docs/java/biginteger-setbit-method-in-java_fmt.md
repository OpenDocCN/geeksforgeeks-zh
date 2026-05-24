# Java中的`BigInteger setBit()`方法

> 原文：[https://www.geeksforgeeks.org/biginteger-setbit-method-in-java/](https://www.geeksforgeeks.org/biginteger-setbit-method-in-java/)

`java.math.BigInteger.setBit(int index)`方法返回一个大整数，该大整数的值相当于设置了指定位的这个大整数。该方法计算`(this | (1 << n))`。大整数二进制表示的索引`n`处的位将被置位，意味着转换为1。

## 语法

```java
public BigInteger setBit(int n)
```

## 参数

该方法取一个参数`n`，指需要设置的位的索引。

## 返回值

该方法在设置位位置`n`后返回`BigInteger`值。

## 异常

当`n`为负时，该方法可能会抛出`ArithmeticException`。

## 示例

```java
Input: value = 2300 index = 1
Output: 2302
Explanation:
Binary Representation of 2300 = 100011111100
bit at index 3 is 1 so set the bit at index 1 
Now Binary Representation becomes 100011111110
and Decimal equivalent of 100011111110 is 2302

Input: value = 5482549 index = 1
Output: 5482551
```

下面的程序说明了`BigInteger`的`setBit(int index)`方法：

```java
// Program to demonstrate setBit() method of BigInteger

import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger biginteger = new BigInteger("2300");

        // Creating an integer i for index
        int i = 1;

        // Calling setBit() method on bigInteger at index i
        // store the return BigInteger
        BigInteger changedvalue = biginteger.setBit(i);

        String result = "After applying setBit at index " + 
            i + " of " + biginteger+ " New Value is " + changedvalue;

        // Displaying the result
        System.out.println(result);
    }
}
```

## 输出

```java
After applying setBit at index 1 of 2300 New Value is 2302
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#setBit(int)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#setBit(int))