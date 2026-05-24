# Java 中的 BigDecimal divideToIntegralValue()方法，带示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-dividetointegralvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-dividetointegralvalue-method-in-java-with-examples/)

用于计算两个大小数的商的整数部分 **(this / divisor)** 向下舍入。结果的优选尺度是 (`this.scale()` – `divisor.scale()`)。此方法对调用此方法的当前大十进制数和作为参数传递的大十进制数执行操作。

## Java 中有两种 divideToIntegralValue 方法重载

*   `divideToIntegralValue(BigDecimal divisor)`
*   `divideToIntegralValue(BigDecimal divisor, MathContext mc)`

### `divideToIntegralValue(BigDecimal divisor)`

**语法:**

```java
public BigDecimal divideToIntegralValue(BigDecimal divisor)
```

**参数:** 这个方法接受一个参数 `divisor`，这个大十进制数将除以这个参数。
**返回值:** 这个方法返回一个 `BigDecimal`，保存结果的整数部分 **(this / divisor)**。
**异常:** 参数 `divisor` 一定不能为 `0`，否则抛出 `ArithmeticException`。

下面的程序用来说明大十进制的 `divideToIntegralValue()` 方法。

```java
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "31452678569";
        String input2
            = "2468";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divideToIntegralValue() method
        res = a.divideToIntegralValue(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java

```

### `divideToIntegralValue(BigDecimal divisor, MathContext mc)`

由于精确商的整数部分不依赖于舍入模式，因此舍入模式不影响此方法返回的值。结果的优选尺度是 (`this.scale()` – `divisor.scale()`)。

**语法:**

```java
public BigDecimal divideToIntegralValue(BigDecimal divisor,
                                        MathContext mc)
```

**参数:** 该方法接受一个参数 `divisor` 和一个参数 `mc` (`MathContext`) 进行上下文设置。
**返回值:** 该方法返回一个大十进制数，保存结果的整数部分 **(this / divisor)**。
**异常:** 该方法针对以下情况抛出 `ArithmeticException`:

*   参数 `divisor` 不得为 `0`。
*   如果 `mc.precision > 0` 并且结果需要超过 `mc.precision` 位数的精度。

下面的程序用来说明大十进制的 `divideToIntegralValue()` 方法。

**例 1:**

```java
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "24536482";
        String input2
            = "2";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);

        // Using divideToIntegralValue() method
        res = a.divideToIntegralValue(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java

```

**示例 2:** 说明 `divideToIntegralValue()` 方法中发生异常的程序

```java
// Java program to demonstrate
// divideToIntegralValue() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "24536482";
        String input2
            = "2";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        // As the result requires
        // a precision of more than
        // mc.precision digits
        // So Exception occur
        try {

            // Using divideToIntegralValue() method
            res = a.divideToIntegralValue(divisor, mc);

            // Display the result in BigDecimal
            System.out.println(res);
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.ArithmeticException: Division impossible
```

**参考文献:** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideToIntegralValue(java.math.BigDecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideToIntegralValue(java.math.BigDecimal))