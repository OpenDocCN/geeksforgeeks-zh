# Java 中的 BigInteger clearBit()方法

> 原文: [`https://www.geeksforgeeks.org/biginteger-clearbit-method-in-java/`](https://www.geeksforgeeks.org/biginteger-clearbit-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

`clearBit()`方法返回一个`BigInteger`，用于清除大整数中的特定位位置。`BigInteger`的二进制表示的索引`n`处的位将被清除，意味着转换为零。数学上我们可以说是用来计算`this & ~(1 << n)`。

**语法:**

```java
public BigInteger clearBit(int n)
```

**参数:** 该方法取一个参数`n`，指需要清零的位的索引。
**返回值:** 该方法在清除位位置`n`后返回`BigInteger`。
**抛出:** 当`n`为负时，该方法可能抛出`ArithmeticException`。

**举例:**

```java
Input: value = 2300, index = 3
Output: 2292
Explanation:
Binary Representation of 2300 = 100011111100
bit at index 3 is 1 so clear the bit at index 3 
Now Binary Representation becomes 100011110100
and Decimal equivalent of 100011110100 is 2292

Input: value = 5482549, index = 0
Output: 5482548
```

下面的程序说明了`BigInteger`的`clearBit(int)`方法。

## 示例代码

```java
/*
*Program Demonstrate clearBit() method of BigInteger
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger biginteger = new BigInteger("5482549");

        // Creating an int i for index
        int i = 0;

        // Call clearBit() method on bigInteger at index i
        // store the return BigInteger
        BigInteger changedvalue = biginteger.clearBit(i);

        String result = "After applying clearbit at index " +
            i + " of " + biginteger+" New Value is " + changedvalue;

        // Print result
        System.out.println(result);
    }
}
```

**Output:**

```java
After applying clearbit at index 0 of 5482549 New Value is 5482548
```

**参考:** [`https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#clearBit(int)`](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#clearBit(int))