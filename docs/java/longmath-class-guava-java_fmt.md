# LongMath 类 | 番石榴 | Java

> 原文: [https://www.geeksforgeeks.org/longmath-class-guava-java/](https://www.geeksforgeeks.org/longmath-class-guava-java/)

`LongMath` 用于对 `Long` 值进行数学运算。基本的独立数学函数根据所涉及的主要数值类型分为类 `IntMath`、`LongMath`、`DoubleMath`。这些类具有并行结构，但每个都只支持相关的函数子集。

## 申报

申报为 `@GwtCompatible(emulated = true)` 的类为：

```java
@GwtCompatible(emulated = true)
public final class LongMath
   extends Object
```

下表显示了番石榴 `LongMath` 类提供的一些方法:
![](img/bc5a1662d337a590bd1a6943aaf84f83.png)

## 例外

*   `log2`: `IllegalArgumentException` if x <= 0
*   `log10`: `IllegalArgumentException` if x <= 0
*   `pow`: `IllegalArgumentException` if k < 0
*   `sqrt`: `IllegalArgumentException` if x < 0
*   `divide`: `ArithmeticException` if q == 0，或者如果 mode == UNNECESSARY 且 a 不是 b 的整数倍
*   `mod`: `ArithmeticException` if m <= 0
*   `gcd`: `IllegalArgumentException` if a < 0 或 b < 0
*   `checkedAdd`: `ArithmeticException` 如果 a + b 在有符号长算术中溢出
*   `checkedSubtract`: `ArithmeticException` 如果 a – b 在有符号长算术中溢出
*   `checkedMultiply`: `ArithmeticException` 如果 a * b 在有符号长算术中溢出
*   `checkedPow`: `ArithmeticException` 如果 b 的 k 次方在有符号长算术中溢出
*   `factorial`: `IllegalArgumentException` if n < 0
*   `binomial`: `IllegalArgumentException` if n < 0，k < 0 或 k > n

番石榴 `LongMath` 类提供的其他一些方法有:
![](img/7f2f35ae44f5cf9927b92a40b00c2106.png)

## 例 1

```java
// Java code to show implementation of
// LongMath Class of Guava
import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        // Creating an object of GFG class
        GFG obj = new GFG();

        // Function calling
        obj.examples();
    }

    private void examples()
    {
        try {
            // exception will be thrown as 80 is not
            // completely divisible by 3
            // thus rounding is required, and
            // RoundingMode is set as UNNESSARY
            System.out.println(LongMath.divide(80, 3, RoundingMode.UNNECESSARY));
        }
        catch (ArithmeticException ex) {
            System.out.println("Error Message is : " + ex.getMessage());
        }
    }
}
```

输出:

```java
Error Message is : mode was UNNECESSARY, but rounding was necessary
```

## 例 2

```java
// Java code to show implementation of
// LongMath Class of Guava
import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        // Creating an object of GFG class
        GFG obj = new GFG();

        // Function calling
        obj.examples();
    }

    private void examples()
    {
        // As 120 is divisible by 4, so
        // no exception is thrown
        System.out.println(LongMath.divide(120, 4, RoundingMode.UNNECESSARY));

        // To compute GCD of two integers
        System.out.println("GCD is : " + LongMath.gcd(70, 14));

        // To compute log to base 10
        System.out.println("Log10 is : " + LongMath.log10(1000, RoundingMode.HALF_EVEN));

        // To compute remainder
        System.out.println("modulus is : " + LongMath.mod(125, 5));

        // To compute factorial
        System.out.println("factorial is : " + LongMath.factorial(7));

        // To compute log to base 2
        System.out.println("Log2 is : " + LongMath.log2(8, RoundingMode.HALF_EVEN));

        // To compute square root
        System.out.println("sqrt is : " + LongMath.sqrt(LongMath.pow(12, 2), RoundingMode.HALF_EVEN));
    }
}
```

输出:

```java
GCD is : 14
Log10 is : 3
modulus is : 0
factorial is : 5040
Log2 is : 3
sqrt is : 12
```

## 参考

谷歌番石榴