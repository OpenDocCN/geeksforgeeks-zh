# BigIntegerMath.sqrt() 函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/bigintegermath-sqrt-function-guava-java/](https://www.geeksforgeeks.org/bigintegermath-sqrt-function-guava-java/)

[Guava 的 `BigIntegerMath`](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/) 类的 `sqrt(BigInteger x, RoundingMode mode)` 方法返回 `x` 的**平方根**，并使用指定的舍入模式进行舍入。

## 语法

```java
public static BigInteger sqrt(BigInteger x, RoundingMode mode)
```

## 参数

该方法接受以下参数：

*   `x`：要计算平方根的大整数。
*   `mode`：用于计算平方根的舍入模式。

## 返回值

该方法返回 `x` 的**平方根**，并使用指定的舍入方式进行舍入。

## 异常

此方法抛出以下异常：

*   `IllegalArgumentException`：如果 `x < 0`。
*   `ArithmeticException`：如果 `mode` 是 `UNNECESSARY` 模式，但 `sqrt(x)` 不是整数。

## 枚举 RoundingMode

| 枚举常数 | 描述 |
| :--- | :--- |
| `CEILING` | 向正无穷大方向舍入。 |
| `DOWN` | 向零方向舍入。 |
| `FLOOR` | 向负无穷大方向舍入。 |
| `HALF_DOWN` | 向最接近的相邻数字舍入，如果两个相邻数字等距，则向 `DOWN` 方向舍入。 |
| `HALF_EVEN` | 向最接近的相邻数字舍入，如果两个相邻数字等距，则向偶数相邻数字舍入。 |
| `HALF_UP` | 向最接近的相邻数字舍入，如果两个相邻数字等距，则向上舍入。 |
| `UNNECESSARY` | 断言请求的操作具有确切的结果，因此不需要舍入。 |
| `UP` | 向远离零的方向舍入。 |

## 示例

以下示例说明了 `BigIntegerMath.sqrt()` 方法：

### 示例 1

```java
// Java code to show implementation of
// sqrt(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger x1 = BigInteger.valueOf(226);

        // Using sqrt(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the nearest neighbor unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        BigInteger ans1 = BigIntegerMath
                              .sqrt(x1,
                                    RoundingMode.HALF_EVEN);

        System.out.println("Square root of " + x1
                           + " with HALF_EVEN rounding mode is: "
                           + ans1);

        BigInteger x2 = BigInteger.valueOf(154);

        // Using sqrt(BigInteger x, RoundingMode mode)
        // method of Guava's BigIntegerMath class
        // The RoundingMode FLOOR rounds towards
        // negative infinity.
        BigInteger ans2 = BigIntegerMath
                              .sqrt(x2,
                                    RoundingMode.FLOOR);

        System.out.println("Square root of " + x2
                           + " with FLOOR rounding mode is: "
                           + ans2);
    }
}
```

**输出：**

```java
Square root of 226 with HALF_EVEN rounding mode is: 15
Square root of 154 with FLOOR rounding mode is: 12
```

### 示例 2

```java
// Java code to show implementation of
// sqrt(BigInteger x, RoundingMode mode) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            BigInteger x1 = BigInteger.valueOf(-65);

            // Using sqrt(BigInteger x, RoundingMode mode)
            // method of Guava's BigIntegerMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the nearest neighbor unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            BigInteger ans1 = BigIntegerMath
                                  .sqrt(x1,
                                        RoundingMode.HALF_EVEN);

            // This should throw "IllegalArgumentException"
            // as x1 < 0
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.IllegalArgumentException: x (-65) must be >= 0
```

## 参考

[https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#sqrt-java.math.BigInteger-java.math.RoundingMode-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#sqrt-java.math.BigInteger-java.math.RoundingMode-)