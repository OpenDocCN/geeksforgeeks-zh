# Java 中的 BigDecimal divideAndRemainder()方法，带示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-divideandremainder-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-divideandremainder-method-in-java-with-examples/)

`BigDecimal.divideAndRemainder(BigDecimal divisor)` 用于计算两个 `BigDecimal` 的**商**和**余数**。如果整数商和余数都需要，那么这种方法比分别使用 `divideToIntegralValue()` 和 `remainder()` 方法更快，因为除法只需要执行一次。此方法对调用此方法的当前 `BigDecimal` 和作为参数传递的 `BigDecimal` 执行操作。

Java 中有两个 `divideAndRemainder` 方法的重载，如下所示：

*   `divideAndRemainder(BigDecimal divisor)`
*   `divideAndRemainder(BigDecimal divisor, MathContext mc)`

### `divideAndRemainder(BigDecimal divisor)`

**语法：**

```java
public BigDecimal[] divideAndRemainder(BigDecimal divisor)
```

**参数：** 这个方法接受一个参数 `divisor`，这个 `BigDecimal` 要除以这个参数才能得到余数和商。
**返回值：** 这个方法返回一个大小为二的 `BigDecimal` 数组，它保存**商**和**余数**。
**异常：** 参数 `divisor` 一定不能为 `0`，否则抛出 `ArithmeticException`。

下面的程序是用来说明 `divideAndRemainder()` 方法的 `BigDecimal`。

```java
// Java program to demonstrate
// divideAndRemainder() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "456865265569";
        String input2
            = "65245";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divideAndRemainder() method
        res = a.divideAndRemainder(divisor);

        // Display the result in BigDecimal
        System.out.println("Quotient = " + res[0]
                           + "\nRemainder = " + res[1]);
    }
}
```

**Output:**

```java
Quotient = 7002303
Remainder = 6334
```

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideToIntegralValue(java.math.BigDecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideToIntegralValue(java.math.BigDecimal))

### `divideAndRemainder(BigDecimal divisor, MathContext mc)`

该方法用于计算商，该商是对根据上下文设置通过舍入计算的两个操作数的 `divideToIntegralValue()` 的结果，然后是 `remainder()` 的结果。

**语法：**

```java
public BigDecimal[] divideAndRemainder(BigDecimal divisor, 
                                       MathContext mc)
```

**参数：** 该方法接受两个参数：

*   `divisor`：除以这个 `BigDecimal` 的数。
*   `mc`：上下文设置的 `MathContext` 类型。

**返回值：** 这个方法返回一个大小为二的 `BigDecimal` 数组，其中保存了**商**和**余数**。

**异常：** 该方法针对以下情况抛出 `ArithmeticException`：

*   如果参数 `divisor` 为 `0`。
*   如果结果不精确，但舍入模式是 `UNNECESSARY` 或 `precision > 0`，并且 `this.divideToIntegralValue(divisor)` 的结果需要超过精度位数的精度。

下面的程序是用来说明 `divideAndRemainder()` 方法的 `BigDecimal`。

**程序 1：**

```java
// Java program to demonstrate
// divideAndRemainder() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "4568652655";
        String input2
            = "2562";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);

        try {
            // Using divideAndRemainder() method
            res = a.divideAndRemainder(divisor, mc);

            // Display the result in BigDecimal
            System.out.println("Quotient = " + res[0]
                               + "\nRemainder = " + res[1]);
        }
        catch (Exception e) {

            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Quotient = 1783236
Remainder = 2023
```

**程序 2：** 显示方法 `divideAndRemainder()` 引发的异常的程序。

```java
// Java program to demonstrate
// divideAndRemainder() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store the result
        BigDecimal res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values
        String input1
            = "4568652655";
        String input2
            = "2562";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        try {
            // Using divideAndRemainder() method
            res = a.divideAndRemainder(divisor, mc);

            // Display the result in BigDecimal
            System.out.println("Quotient = " + res[0]
                               + "\nRemainder = "
                               + res[1]);
        }
        catch (Exception e) {

            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.ArithmeticException: Division impossible
```

**参考文献：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideAndRemainder(java.math.BigDecimal, java.math.MathContext)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divideAndRemainder(java.math.BigDecimal, java.math.MathContext))