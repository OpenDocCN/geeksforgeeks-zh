# BigIntegerMath.log2()函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/bigintegermath-log2-function-guava-java/](https://www.geeksforgeeks.org/bigintegermath-log2-function-guava-java/)

[Guava的`BigIntegerMath`类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法`log2(BigInteger x, RoundingMode mode)`返回`x`的以2为底的对数，根据指定的舍入模式进行舍入。

**语法：**

```java
public static int log2(BigInteger x, RoundingMode mode)
```

**参数：** 该方法取以下参数：
*   `x`：一个你想求其对数的大整数。
*   `mode`：用于计算以2为底的对数的舍入模式。

**返回值：** 该方法返回`x`的以2为底的对数，根据指定的舍入方式进行舍入。

**异常：** 此方法抛出以下异常：
*   `IllegalArgumentException`：如果`x <= 0`。
*   `ArithmeticException`：如果`mode`是`UNNECESSARY`模式，但`x`不是2的幂。

## 枚举舍入模式

| 枚举常数 | 描述 |
| :--- | :--- |
| `CEILING` | 舍入模式向正无穷大舍入。 |
| `DOWN` | 舍入模式为向零舍入。 |
| `FLOOR` | 舍入模式为向负无穷大舍入。 |
| `HALF_DOWN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下舍入为`DOWN`。 |
| `HALF_EVEN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| `HALF_UP` | 取整模式为向“最近邻居”取整，除非两个邻居等距，在这种情况下取整。 |
| `UNNECESSARY` | 舍入模式断言请求的操作有确切的结果，因此没有舍入的必要。 |
| `UP` | 取整模式为远离零取整。 |

以下示例说明了`BigIntegerMath.log2()`方法：

### 例 1

```java
// Java code to show implementation of
// log2(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger a1 = BigInteger.valueOf(1024);

        // Using log2(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println("Log base 2 of " + a1
                           + " with rounding mode HALF_EVEN = "
                           + BigIntegerMath
                                 .log2(a1,
                                        RoundingMode.HALF_EVEN));

        BigInteger a2 = BigInteger.valueOf(15);

        // Using log2(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println("Log base 2 of " + a2
                           + " with rounding mode HALF_DOWN = "
                           + BigIntegerMath
                                 .log2(a2,
                                        RoundingMode.HALF_DOWN));
    }
}
```

**输出：**

```java
Log base 2 of 1024 with rounding mode HALF_EVEN = 10
Log base 2 of 15 with rounding mode HALF_DOWN = 1
```

### 示例 2：显示非法参数异常

```java
// Java code to show implementation of
// log2(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        try {
            BigInteger a1 = BigInteger.valueOf(-5);

            // Using log2(BigInteger x, RoundingMode mode)
            // method of Guava's BigIntegerMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as a1 <= 0
            System.out.println("Log base 2 of " + a1
                               + " with rounding mode HALF_EVEN = "
                               + BigIntegerMath
                                     .log2(a1,
                                            RoundingMode.HALF_EVEN));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.IllegalArgumentException: x (-5) must be > 0
```

**参考：** [https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#log2-java.math.BigInteger-java.math.RoundingMode-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#log2-java.math.BigInteger-java.math.RoundingMode-)