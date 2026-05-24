# Java 中的 BigDecimal.negate() 函数

> 原文：`https://www.geeksforgeeks.org/bigdecimal-negate-function-in-java/`

## 1. `BigDecimal.negate()` 方法

`java.math.BigDecimal.negate()` 方法返回一个 `BigDecimal`，其值是该 `BigDecimal` 的相反数。

**语法：**

```java
public BigDecimal negate()
```

**参数：** 该方法不接受任何参数。

**返回值：** 该方法返回 `BigDecimal` 对象的负值，其小数位数为 `this.scale()`。

下面的程序将举例说明 `java.math.BigDecimal.negate()` 函数的使用：

**程序 1：**

```java
// Java program to demonstrate negate() method
import java.math.*;

public class GFG {
    public static void main(String[] args) {
        // Create a BigDecimal object
        BigDecimal num;

        // Assign value to num
        num = new BigDecimal("4743");

        System.out.println("Negated value is " + num.negate());
    }
}
```

**输出：**

```java
Negated value is -4743
```

**程序 2：**

```java
// Java program to demonstrate negate() method
import java.math.*;

public class GFG {
    public static void main(String[] args) {
        // Create a BigDecimal object
        BigDecimal num;

        // Assign value to num
        num = new BigDecimal("-9674283517.97");

        System.out.println("Negated value is " + num.negate());
    }
}
```

**输出：**

```java
Negated value is 9674283517.97
```

## 2. `BigDecimal.negate(MathContext mc)` 方法

`java.math.BigDecimal.negate(MathContext mc)` 方法返回一个 `BigDecimal`，其值是它的相反数，即根据 `MathContext` 类对象指定的精度设置进行舍入后得到的值。

**语法：**

```java
public BigDecimal negate(MathContext mc)
```

**参数：** 该方法只接受 `MathContext` 类对象的一个参数 `mc`，该参数指定舍入时的精度设置。

**返回值：** 该方法返回对象的求反值，该值根据精度设置进行舍入。

**异常：** 如果得到的结果不准确，但舍入模式不必要，该方法可能会抛出 `ArithmeticException`。

下面的程序将举例说明 `java.math.BigDecimal.negate(MathContext mc)` 方法的使用：

**程序 1：**

```java
// Java program to demonstrate negate(MathContext mc) method
import java.math.*;

public class GFG {
    public static void main(String[] args) {
        // create 2 BigDecimal objects
        BigDecimal num, negv;

        MathContext mc = new MathContext(4); // 4 precision

        // assign value to num
        num = new BigDecimal("78.6714");

        // assign negate value of num to negv using mc
        negv = num.negate(mc);
        System.out.println("Negated value, rounded to 4 precision " + negv);
    }
}
```

**输出：**

```java
Negated value, rounded to 4 precision -78.67
```

**程序 2：**

```java
// Java program to demonstrate negate(MathContext mc) method
import java.math.*;

public class GFG {
    public static void main(String[] args) {
        // create 2 BigDecimal objects
        BigDecimal num, negv;

        MathContext mc = new MathContext(12); // 12 precision

        // assign value to num
        num = new BigDecimal("-178901456.68431");

        // assign negate value of num to negv using mc
        negv = num.negate(mc);
        System.out.println("Negated value, rounded to 12 precision " + negv);
    }
}
```

**输出：**

```java
Negated value, rounded to 12 precision 178901456.684
```

**参考：**
`https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#negate()`