# Java 中的 `BigDecimal remainder()` 方法，示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-remainder-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-remainder-method-in-java-with-examples/)

`remainder(BigDecimal divisor)` 用于计算两个 `BigDecimal` 的余数。余数由此给出：`this.subtract(this.divide(divisor, RoundingMode.DOWN).multiply(divisor))`。此方法对调用此方法的当前 `BigDecimal` 数和作为参数传递的 `BigDecimal` 数执行操作。

**注意：** 这不是模运算（结果可以是负数）。

Java 中有两种 `remainder` 方法重载，如下所示：

*   `remainder(BigDecimal divisor)`
*   `remainder(BigDecimal divisor, MathContext mc)`

### `remainder(BigDecimal divisor)`

**语法：**

```java
public BigDecimal remainder(BigDecimal divisor)
```

**参数：** 这个方法接受一个参数 `divisor`，这个 `BigDecimal` 要除以这个参数才能得到余数。

**返回值：** 这个方法返回一个 `BigDecimal`，保存结果 `(this % divisor)`。

**异常：** 参数 `divisor` 一定不能为 `0`，否则抛出 `ArithmeticException`。

下面的程序用来说明 `BigDecimal` 的 `remainder()` 方法。

```java
// Java program to demonstrate
// remainder() method of BigDecimal

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

        // Using remainder() method
        res = a.remainder(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**输出：**

```java

```

### `remainder(BigDecimal divisor, MathContext mc)`

该方法用于计算值为 `(this % divisor)` 的两个 `BigDecimal` 的余数，根据上下文设置进行四舍五入。`MathContext` 设置影响用于计算余数的隐式除法。因此，余数可能包含超过 `mc.getPrecision()` 位的数字。

**语法：**

```java
public BigDecimal remainder(BigDecimal divisor, MathContext mc)
```

**参数：** 这个方法接受一个参数 `divisor`，这个 `BigDecimal` 将被这个除数除，以及一个类型为 `MathContext` 的参数 `mc` 用于上下文设置。

**返回值：** 这个方法返回一个 `BigDecimal`，保存结果 `(this % divisor)`。

**异常：** 方法抛出 `ArithmeticException` 以下情况：

*   参数 `divisor` 必须不为 `0`。
*   如果 `mc.getPrecision() > 0` 且结果所需精度超过 `mc.getPrecision()` 位数字。

下面的程序是用来说明 `BigDecimal` 的 `remainder()` 方法的。

```java
// Java program to demonstrate
// remainder() method of BigDecimal

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
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        // Using remainder() method
        res = a.remainder(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**输出：**

```java

```

**参考文献：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#remainder(java.math.BigDecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#remainder(java.math.BigDecimal))