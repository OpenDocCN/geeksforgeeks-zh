# Java 中的 BigDecimal divide()方法，示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-divide-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-divide-method-in-java-with-examples/)

`divide(BigDecimal)` 用于计算两个 `BigDecimal` 的**商**。**商**由 **(this / divisor)** 给出。此方法对调用此方法的当前 `BigDecimal` 数和作为参数传递的 `BigDecimal` 数执行操作。

Java 中有五个 `divide` 方法重载，如下所示：

*   `divide(BigDecimal divisor)`
*   `divide(BigDecimal divisor, MathContext mc)`
*   `divide(BigDecimal divisor, RoundingMode roundingMode)`
*   `divide(BigDecimal divisor, int scale, RoundingMode roundingMode)`
*   `divide(BigDecimal divisor, int scale)`

**注：** 方法 `divide(BigDecimal divisor, int scale)` 因 **Java 9** 而被弃用。

## divide(BigDecimal divisor)

**商**由 **(this / divisor)** 给出，其优选标度是 (`this.scale()` – `divisor.scale()`)。

**语法：**

```java
public BigDecimal divide(BigDecimal divisor)
```

**参数：** 这个方法接受一个参数 `divisor`，这个 `BigDecimal` 要除以这个参数才能得到商。
**返回值：** 这个方法返回一个 `BigDecimal`，保存结果 **(this / divisor)**。
**异常：** 如果参数 `divisor` 为 **0** 或者精确商没有终止十进制展开，则抛出 `ArithmeticException`。

下面的程序用来说明 `BigDecimal` 的 `divide()` 方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "204800000";
        String input2
            = "256";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divide() method
        res = a.divide(divisor);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java

```

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal))

## divide(BigDecimal divisor, MathContext mc)

该方法用于计算值为 **(this / divisor)** 的两个 `BigDecimal` 的商，根据上下文设置取整。

**语法：**

```java
public BigDecimal divide(BigDecimal divisor,
                         MathContext mc)
```

**参数：** 该方法接受两个参数：

*   `divisor` 除以这个 `BigDecimal` 数
*   上下文设置的 `MathContext` 类型的 `mc`。

**返回值：** 该方法返回一个 `BigDecimal`，保存结果 **(this / divisor)**，并根据需要进行舍入。

**异常：** 如果结果不精确，但舍入模式为不必要或 `mc.precision == 0`，并且商具有非终止十进制展开，则该方法抛出 `ArithmeticException`。

下面的程序用来说明 `BigDecimal` 的 `divide()` 方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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

        // Using divide() method
        res = a.divide(divisor, mc);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java

```

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.MathContext)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.MathContext))

## divide(BigDecimal divisor, RoundingMode roundingMode)

**商**由 **(this / divisor)** 给出，其优选标度是 `this.scale()`。如果需要舍入来生成给定比例的结果，则应用特定的舍入模式。

**语法：**

```java
public BigDecimal divide(BigDecimal divisor,
                         RoundingMode roundingMode)
```

**参数：** 该方法接受两个参数：

*   `divisor` 除以这个 `BigDecimal` 数
*   `RoundingMode` 类型的 `roundingMode`，告知应用哪种舍入模式。

**返回值：** 这个方法返回一个 `BigDecimal`，保存结果 **(this / divisor)**。
**异常：** 如果 `roundingMode` 不必要且 `this.scale()` 不足以准确表示除法结果或 `divisor` 为 0，则该方法抛出 `ArithmeticException`。

下面的程序用来说明 `BigDecimal` 的 `divide()` 方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "2453648454542";
        String input2
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using divide() method
        // Using RoundingMode.CEILING
        res = a.divide(divisor, RoundingMode.CEILING);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java

```

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.RoundingMode)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, java.math.RoundingMode))

## divide(BigDecimal divisor, int scale, RoundingMode roundingMode)

**商**由 **(this / divisor)** 给出，其优选标度是指定的。如果需要舍入来生成具有指定比例的结果，则应用指定的舍入模式。

**语法：**

```java
public BigDecimal divide(BigDecimal divisor, 
                         int scale, 
                         RoundingMode roundingMode)
```

**参数：** 该方法接受三个参数：

*   `divisor` 除以这个 `BigDecimal` 数
*   `RoundingMode` 类型的 `roundingMode`，告知应用哪种舍入模式
*   `scale` 设置商的刻度。

**返回值：** 这个方法返回一个 `BigDecimal`，保存结果 **(this / divisor)**。
**异常：** 如果舍入模式不必要且指定的小数位数不足以准确表示除法结果或 `divisor` 为 0，则该方法抛出 `ArithmeticException`。

下面的程序用来说明 `BigDecimal` 的 `divide()` 方法。

```java
// Java program to demonstrate
// divide() method of BigDecimal

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
            = "2453648454542";
        String input2
            = "264";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal divisor
            = new BigDecimal(input2);

        // Using scale = 4
        int scale = 4;

        // Using divide() method
        // Using RoundingMode.CEILING
        res = a.divide(divisor, scale,
                       RoundingMode.CEILING);

        // Display the result in BigDecimal
        System.out.println(res);
    }
}
```

**Output:**

```java
9294122933.8713
```

**参考：** [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, int, java.math.RoundingMode)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#divide(java.math.BigDecimal, int, java.math.RoundingMode))