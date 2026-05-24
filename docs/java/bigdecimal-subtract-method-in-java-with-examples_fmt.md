# Java 中的 `BigDecimal` `subtract()` 方法，示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-subtract-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-subtract-method-in-java-with-examples/)

`subtract(BigDecimal val)` 用于计算两个 `BigDecimal` 的算术差。这种方法用于在不影响结果精度的情况下找出大数的算术差。此方法对调用此方法的当前 `BigDecimal` 数执行操作，并将 `BigDecimal` 数作为参数传递。

Java 中有两个 `subtract` 方法的重载，如下所示：

*   `subtract(BigDecimal val)`
*   `subtract(BigDecimal val, MathContext mc)`

## `subtract(BigDecimal val)`

**语法：**

```java
public BigDecimal subtract(BigDecimal val)
```

**参数：** 该方法接受参数 `val`，该值是要从该 `BigDecimal` 中减去的值。

**返回值：** 此方法返回一个 `BigDecimal`，它保存差值 (`this - val`)，其小数位数为 `max(this.scale(), val.scale())`。

下面的程序是用来说明 `BigDecimal` 的 `subtract()` 方法的。

```java
// Java program to demonstrate
// subtract() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store result
        BigDecimal diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1
            = "545456468445645468464645";
        String input2
            = "425645648446468486486452";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Using subtract() method
        diff = a.subtract(b);

        // Display the result in BigDecimal
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff + "\n");
    }
}
```

**输出：**

> 545456468445645468464645
> 和
> 425645648446468486486452
> 的区别是
> 119810819998176981978193

## `subtract(BigDecimal val, MathContext mc)`

**语法：**

```java
public BigDecimal subtract(BigDecimal val, MathContext mc)
```

**参数：** 该方法接受两个参数，一个是 `val`，这是要从该 `BigDecimal` 中减去的值，另一个是 `MathContext` 类型的 `mc`。

**返回值：** 该方法返回一个保存差值 (`this - val`) 的 `BigDecimal`，根据上下文设置进行舍入。

下面的程序是用来说明 `BigDecimal` 的 `subtract()` 方法的。

```java
// Java program to demonstrate
// subtract() method of BigDecimal

import java.math.*;

public class GFG {
    public static void main(String[] args)
    {
        // BigDecimal object to store result
        BigDecimal diff;

        // For user input
        // Use Scanner or BufferedReader

        // Two objects of String created
        // Holds the values to calculate the difference
        String input1
            = "468445645468464645";
        String input2
            = "4256456484464684864864";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);
        BigDecimal b
            = new BigDecimal(input2);

        // Set precision to 10
        MathContext mc
            = new MathContext(10);
        // Using subtract() method
        diff = a.subtract(b, mc);

        // Display the result in BigDecimal
        System.out.println("The difference of\n"
                           + a + " \nand\n" + b + " "
                           + "\nis\n" + diff + "\n");
    }
}
```

**输出：**

> 468445645468464645
> 和
> 4256456484464684864864
> 的区别是
> -4.255988039E+21

**参考文献：** [https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#subtract(java.math.BigDecimal)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#subtract(java.math.BigDecimal))