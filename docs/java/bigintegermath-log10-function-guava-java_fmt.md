# BigIntegerMath.log10()函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/bigintegermath-log10-function-guava-java/](https://www.geeksforgeeks.org/bigintegermath-log10-function-guava-java/)

[Guava的`BigIntegerMath`类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法`log10(BigInteger x, RoundingMode mode)`返回`x`的以10为底的对数，根据指定的舍入模式进行舍入。

## 语法

```java
public static int log10(BigInteger x, RoundingMode mode)
```

## 参数

该方法取以下参数：

*   `x`：一个大的整数，你想求其对数。
*   `mode`：计算以10为底的对数时使用的舍入模式。

## 返回值

该方法返回`x`的以10为底的对数，根据指定的舍入方式进行舍入。

## 异常

此方法抛出以下异常：

*   `IllegalArgumentException`：如果`x <= 0`。
*   `ArithmeticException`：如果`mode`是`UNNECESSARY`模式，但`x`不是10的幂。

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

## 示例

以下示例说明了`BigIntegerMath.log10()`方法：

### 示例 1

```java
// Java code to show implementation of
// log10(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger a1 = BigInteger.valueOf(10000);

        // Using log10(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println("Log base 10 of " + a1
                           + " with rounding mode HALF_EVEN = "
                           + BigIntegerMath
                                 .log10(a1,
                                        RoundingMode.HALF_EVEN));

        BigInteger a2 = BigInteger.valueOf(15);

        // Using log10(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println("Log base 10 of " + a2
                           + " with rounding mode HALF_DOWN = "
                           + BigIntegerMath
                                 .log10(a2,
                                        RoundingMode.HALF_DOWN));
    }
}
```

**输出：**

```java
Log base 10 of 10000 with rounding mode HALF_EVEN = 4
Log base 10 of 15 with rounding mode HALF_DOWN = 1
```

### 示例 2：显示非法参数异常

```java
// Java code to show implementation of
// log10(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            BigInteger a1 = BigInteger.valueOf(-5);

            // Using log10(BigInteger x, RoundingMode mode)
            // method of Guava's BigIntegerMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as a1 <= 0
            System.out.println("Log base 10 of " + a1
                               + " with rounding mode HALF_EVEN = "
                               + BigIntegerMath
                                     .log10(a1,
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

## 参考

[https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#log10-java.math.BigInteger-java.math.RoundingMode-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#log10-java.math.BigInteger-java.math.RoundingMode-)