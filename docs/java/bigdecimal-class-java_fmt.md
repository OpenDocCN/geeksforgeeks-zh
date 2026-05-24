# Java 中的 BigDecimal 类

> 原文:[https://www.geeksforgeeks.org/bigdecimal-class-java/](https://www.geeksforgeeks.org/bigdecimal-class-java/)

`BigDecimal` 类为算术、小数位数处理、舍入、比较、格式转换和散列提供了对双数的操作。它可以非常精确地处理非常大和非常小的浮点数，但会稍微补偿时间复杂度。
`BigDecimal` 由随机精度整数未缩放值和 32 位整数刻度组成。如果大于或等于零，刻度是小数点右边的位数。如果小于零，数字的未缩放值将乘以 `10^(-scale)`。

示例:

```java
Input : double a=0.03;
        double b=0.04;
        double c=b-a;
        System.out.println(c);
Output :0.009999999999999998

Input : BigDecimal _a = new BigDecimal("0.03");
        BigDecimal _b = new BigDecimal("0.04");
        BigDecimal _c = _b.subtract(_a);
        System.out.println(_c);
Output :0.01
```

## 需要大小数

*   两种 `java` 基元类型(`double` 和 `float`)是浮点数，存储为分数和指数的二进制表示。
*   其他基本类型(布尔除外)是定点数字。与定点数不同，浮点数在大多数情况下会返回一个有小错误的答案(在 `10^-19` 附近)这就是我们在上面的例子中以 `0.0099999999999998` 作为 `0.04-0.03` 的结果的原因。

但是 `BigDecimal` 为我们提供了确切的答案。

```java
// Java Program to illustrate BigDecimal Class

import java.math.BigDecimal;
public class BigDecimalExample
{
    public static void main(String[] args) 
    {
        // Create two new BigDecimals
        BigDecimal bd1 = 
               new BigDecimal("124567890.0987654321");
        BigDecimal bd2 = 
               new BigDecimal("987654321.123456789");

// Addition of two BigDecimals
        bd1 = bd1.add(bd2);
        System.out.println("BigDecimal1 = " + bd1);

// Multiplication of two BigDecimals
        bd1 = bd1.multiply(bd2);
        System.out.println("BigDecimal1 = " + bd1);

// Subtraction of two BigDecimals
        bd1 = bd1.subtract(bd2);
        System.out.println("BigDecimal1 = " + bd1);

// Division of two BigDecimals
        bd1 = bd1.divide(bd2);
        System.out.println("BigDecimal1 = " + bd1);

// BigDecima1 raised to the power of 2
        bd1 = bd1.pow(2);
        System.out.println("BigDecimal1 = " + bd1);

// Negate value of BigDecimal1
        bd1 = bd1.negate();
        System.out.println("BigDecimal1 = " + bd1);
    }    
}        
```

**输出:-**

```java
BigDecimal1 = 1112222211.2222222211
BigDecimal1 = 1098491072963113850.7436076939614540479
BigDecimal1 = 1098491071975459529.6201509049614540479
BigDecimal1 = 1112222210.2222222211
BigDecimal1 = 1237038244911605079.77528397755061728521
BigDecimal1 = -1237038244911605079.77528397755061728521
```

## 申报

```java
double a, b;                
BigDecimal A, B;
```

## 初始化

```java
a = 5.4;
b = 2.3;
A  = BigDecimal.valueOf(5.4);
B  = BigDecimal.valueOf(2.3);
```

如果给你一个双数的字符串表示，那么你可以用下面的方式初始化:

```java
A  = new BigDecimal(“5.4”);
B  = new BigDecimal(“1238126387123.1234”);
```

为了便于初始化，`BigDecimal` 类有一些预定义的常数:

```java
A = BigDecimal.ONE;
// Other than this, available constants
// are BigDecimal.ZERO and BigDecimal.TEN
```

## 数学运算

```java
int c = a + b;
BigDecimal C = A.add(B); 
Other similar function are subtract() , multiply(), divide(), pow()
```

但是所有这些函数，除了以整数为参数的 `pow()`之外，都以 `BigDecimal` 为参数，所以如果我们希望这些带有小数或字符串的运算在传递给函数之前先转换为 `BigDecimal`，如下所示:

```java
String str = “123456789.123456789”;
BigDecimal C = A.add(new BigBigDecimal(str));
double val  = 123456789.123456789;
BigDecimal C = A.add(BigDecimal.valueOf(val));
```

## 从大十进制中提取值

```java
// value should be in limit of double x
double x   =  A.doubleValue();

// To get string representation of BigDecimal A
String z = A.toString();
```

## 对比

```java
if (a < b) {}         // For primitive double
if (A.compareTo(B) < 0)  {} // For BigDecimal
```

实际比较根据值返回 `-1`(小于)、`0`(等于)、`1`(大于)。

为了平等，我们还可以使用:

```java
if (A.equals(B)) {}  // A is equal to B
```

## 大十进制类的方法

1.  `BigDecimal abs()` :这个方法返回一个 `BigDecimal`，它的值是这个 `BigDecimal` 的绝对值，它的小数位数是这个 `scale()`。
2.  `BigDecimal abs(MathContext mc)`:这个方法返回一个 `BigDecimal`，它的值是这个 `big decimal` 的绝对值，根据上下文设置进行舍入。
3.  `BigDecimal add(BigDecimal augend)`:此方法返回一个 `big decimal`，其值为 `(this + augend)`，小数位数为 `max(this.scale(), augend.scale())`。
4.  `BigDecimal add(BigDecimal augend, MathContext mc)` :此方法返回一个 `big decimal`，其值为 `(this + augend)`，根据上下文设置进行取整。
5.  `byte byteValueExact()`:这个方法把这个 `BigDecimal` 转换成一个字节，检查丢失的信息。
6.  `int compareTo(BigDecimal val)`:这个方法将这个 `BigDecimal` 和指定的 `big decimal` 进行比较。
7.  `BigDecimal divide(BigDecimal divisor)`:此方法返回一个 `BigDecimal`，其值为 `(this / divisor)`，首选小数位数为 `(this.scale() - divisor.scale())`；如果无法表示精确的商(因为它有一个非终止的十进制扩展)，则会引发一个 `ArithmeticException`。
8.  `BigDecimal divide(BigDecimal divisor, int scale, RoundingMode roundingMode)` :此方法返回一个 `BigDecimal`，其值为 `(this / divisor)`，其小数位数如指定。
9.  `BigDecimal divide(BigDecimal divisor, MathContext mc)` :此方法返回一个 `BigDecimal`，其值为 `(this / divisor)`，根据上下文设置进行舍入。
10. `BigDecimal divide(BigDecimal divisor, RoundingMode roundingMode)` :此方法返回一个 `BigDecimal`，其值为 `(this / divisor)`，其小数位数为 `this.scale()`。
11. `BigDecimal[] divideAndRemainder(BigDecimal divisor)`:此方法返回一个双元素 `BigDecimal` 数组，该数组包含 `divideToIntegralValue` 的结果，后跟两个操作数的余数结果。
12. `BigDecimal[] divideAndRemainder(BigDecimal divisor, MathContext mc)` :此方法返回一个双元素 `BigDecimal` 数组，该数组包含 `divideToIntegralValue` 的结果，后跟根据上下文设置通过舍入计算的两个操作数的余数结果。
13. `BigDecimal divideToIntegralValue(BigDecimal divisor)`:此方法返回一个 `big decimal`，其值是向下舍入的商 `(this / divisor)` 的整数部分。
14. `BigDecimal divideToIntegralValue(BigDecimal divisor, MathContext mc)` :此方法返回一个 `big decimal`，其值为 `(this / divisor)` 的整数部分。
15. `double doubleValue()`:这个方法把这个 `BigDecimal` 转换成一个 `double`。
16. `boolean equals(Object x)` :这个方法将这个 `BigDecimal` 和指定的 `Object` 进行相等比较。
17. `float floatValue()` :这个方法把这个 `BigDecimal` 转换成一个 `float`。
18. `int hashCode()` :这个方法返回这个 `BigDecimal` 的哈希码。
19. `int intValue()`:这个方法把这个 `BigDecimal` 转换成一个 `int`。
20. `int intValueExact()`:这个方法把这个 `BigDecimal` 转换成一个 `int`，检查丢失的信息。
21. `long longValue()` :这个方法把这个 `BigDecimal` 转换成一个 `long`。
22. `long longValueExact()`:这个方法把这个 `BigDecimal` 转换成一个 `long`，检查丢失的信息。
23. `BigDecimal max(BigDecimal val)`:这个方法返回这个 `BigDecimal` 和 `val` 的最大值。
24. `BigDecimal min(BigDecimal val)`:这个方法返回这个 `BigDecimal` 和 `val` 的最小值。
25. `BigDecimal movePointLeft(int n)` :这个方法返回一个大十进制，相当于这个大十进制的小数点向左移动了 `n` 位。
26. `BigDecimal movePointRight(int n)`:这个方法返回一个 `BigDecimal`，这个 `BigDecimal` 相当于小数点向右移动了 `n` 位。
27. `BigDecimal multiply(BigDecimal multiplicand)` :此方法返回一个 `BigDecimal`，其值为 `(this × multiplicand)`，小数位数为 `(this.scale() + multiplicand.scale())`。
28. `BigDecimal multiply(BigDecimal multiplicand, MathContext mc)` :此方法返回一个 `BigDecimal`，其值为 `(this × multiplicand)`，根据上下文设置取整。
29. `BigDecimal negate()` :此方法返回一个大十进制，其值为 `(-this)`，其小数位数为 `this.scale()`。
30. `BigDecimal negate(MathContext mc)` :此方法返回一个 `BigDecimal`，其值为 `(-this)`，根据上下文设置进行舍入。

31. `BigDecimal negate()`：此方法返回一个值为`(-this)`的`BigDecimal`，根据上下文设置进行取整。
32. `BigDecimal plus()`：此方法返回一个`BigDecimal`，其值为`(+this)`，小数位数为`this.scale()`。
33. `BigDecimal plus(MathContext mc)`：此方法返回一个`BigDecimal`，其值为`(+this)`，根据上下文设置进行舍入。
34. `BigDecimal pow(int n)`：这个方法返回一个`BigDecimal`，它的值是`(this^n)`，幂的计算是精确的，精度是无限的。
35. `BigDecimal pow(int n, MathContext mc)`：这个方法返回一个`BigDecimal`，它的值是`(this^n)`。
36. `int precision()`：这个方法返回这个`BigDecimal`的精度。
37. `BigDecimal remainder(BigDecimal divisor)`：此方法返回一个`BigDecimal`，其值为`(this % divisor)`。
38. `BigDecimal remainder(BigDecimal divisor, MathContext mc)`：此方法返回一个`BigDecimal`，其值为`(this % divisor)`，根据上下文设置进行舍入。
39. `BigDecimal round(MathContext mc)`：此方法根据`MathContext`设置返回一个舍入后的`BigDecimal`。
40. `int scale()`：这个方法返回这个`BigDecimal`的小数位数。
41. `BigDecimal scaleByPowerOfTen(int n)`：此方法返回一个数值等于`(this * 10^n)`的`BigDecimal`。
42. `BigDecimal setScale(int newScale)`：这个方法返回一个`BigDecimal`，它的小数位数是指定的值，数值等于这个`BigDecimal`的数值。
43. `BigDecimal setScale(int newScale, RoundingMode roundingMode)`：此方法返回一个`BigDecimal`，其小数位数为指定值，其未缩放值通过将此`BigDecimal`的未缩放值乘以或除以适当的十次方来确定，以保持其整体值。
44. `short shortValueExact()`：这个方法把这个`BigDecimal`转换成一个`short`，检查丢失的信息。
45. `int signum()`：这个方法返回这个`BigDecimal`的`signum`函数。
46. `BigDecimal sqrt(MathContext mc)`：此方法根据上下文设置，通过舍入返回此的平方根近似值。
47. `BigDecimal stripTrailingZeros()`：此方法返回一个`BigDecimal`，该数在数字上等于这个数，但从表示中删除了任何尾随零。
48. `BigDecimal subtract(BigDecimal subtrahend)`：此方法返回一个`BigDecimal`，其值为`(this – subtrahend)`，其小数位数为`max(this.scale(), subtrahend.scale())`。
49. `BigDecimal subtract(BigDecimal subtrahend, MathContext mc)`：此方法返回一个`BigDecimal`，其值为`(this – subtrahend)`，根据上下文设置进行舍入。
50. `BigInteger toBigInteger()`：这个方法把这个`BigDecimal`转换成`BigInteger`。
51. `BigInteger toBigIntegerExact()`：这个方法把这个`BigDecimal`转换成`BigInteger`，检查丢失的信息。
52. `String toEngineeringString()`：此方法返回此`BigDecimal`的字符串表示形式，如果需要指数，则使用工程符号。
53. `String toPlainString()`：这个方法返回这个`BigDecimal`的字符串表示，没有指数字段。
54. `String toString()`：这个方法返回这个`BigDecimal`的字符串表示形式，如果需要指数，使用科学表示法。
55. `BigDecimal ulp()`：这个方法返回一个`ulp`的大小，这个`BigDecimal`的最后一位的单位。
56. `BigInteger unscaledValue()`：这个方法返回一个`BigInteger`，它的值是这个`BigDecimal`的未缩放值。
57. `static BigDecimal valueOf(double val)`：该方法使用`Double.toString(double)`方法提供的`double`的规范字符串表示形式，将`double`转换为`BigDecimal`。
58. `static BigDecimal valueOf(long val)`：此方法将`long`值转换为小数位数为零的`BigDecimal`。
59. `static BigDecimal valueOf(long unscaledVal, int scale)`：此方法将`long`未缩放值和`int`比例转换为`BigDecimal`。

更多示例请访问 [Java BigDecimal 示例](http://voidexception.weebly.com/java-bigdecimal---dealing-with-high-precision-calculations.html)

**相关文章：**

*   [用 Java 中的 BigDecimal 计算 PI 数，最多 200 位小数](https://stackoverflow.com/questions/27616294/using-bigdecimal-in-java-to-calculate-pi-number-up-to-200-decimal-digits)
*   [Make cents with BigDecimal](https://www.javaworld.com/article/2075315/core-java/make-cents-with-bigdecimal.html)

更多功能及详情请参考 [`BigDecimal`](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html)