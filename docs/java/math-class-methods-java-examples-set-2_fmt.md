# Java 中的数学类方法，带示例|第 2 集

> 原文：[https://www.geeksforgeeks.org/math-class-methods-java-examples-set-2/](https://www.geeksforgeeks.org/math-class-methods-java-examples-set-2/)

[java.math 类及其方法|集 1](https://www.geeksforgeeks.org/java-math-class-methods-set-1/)

[![java.math class methods](img/ab46fa651f08045e0a517edfde628cce.png)](https://media.geeksforgeeks.org/wp-content/uploads/table_math_class-.png)

## 本文讨论的 java.math 类方法：

### 1. `abs()`
`Math.abs()` 方法返回传递的任何类型参数的绝对值。这个方法可以处理所有的数据类型。

**Special Case :**
*   如果参数为正零或负零，则结果为正零。
*   如果参数为无穷大，则结果为正无穷大。
*   如果传递的参数是 NaN，则结果为 NaN。

**语法:**
```java
public static datatype abs(datatype arg)
```
**Parameters:**
`arg` - the argument whose absolute value we need
**Returns:**
absolute value of the passed argument.

### 2. `acos()`
`Math.acos()` 方法返回传递的参数的弧余弦值。
弧余弦是传递的参数的反余弦。
`acos(arg) = cos⁻¹` 的 `arg`

**特例:** 结果为 NaN，如果自变量为 NaN 或其绝对值大于 1。

**语法:**
```java
public static double acos(double a)
```
**Parameters:**
`a` - the argument whose arc cosine value we need. argument is taken as radian
**Returns:**
arc cosine value of the argument.

### 3. `toRadians()`
`Math.toRadians(double deg)` 方法将参数（度）转换为弧度。

**Special Point :** `Math` 类通常以弧度作为输入，这在现实应用中非常不同，因为角度通常以度表示。

**语法:**
```java
public static double toRadians(double deg)
```
**Parameters:**
`deg` - degree angle needs to be in radian.
**Returns:**
radians equivalent of the degree-argument passed.

**什么是 NaN 论证？**
一个持有 `double` 型非数字值的常数。它相当于 `Double.longBitsToDouble(0x7ff8000000000001L)` 返回的值。

**在 `Math` 类中解释 `abs()`、`acos()`、`toRadians()` 方法的 Java 代码。**
```java
// Java program explaining Math class methods
// abs(), acos(), toRadians()
import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Declaring the variables
        int Vali = -1;
        float Valf = .5f;

        // Printing the values
        System.out.println("Initial value of int  : "+Vali);
        System.out.println("Initial value of int  : "+Valf);

        // Use of .abs() method to get the absoluteValue
        int Absi = Math.abs(Vali);
        float Absf = Math.abs(Valf);

        System.out.println("Absolute value of int : "+Absi);
        System.out.println("Absolute value of int : "+Absf);
        System.out.println("");

        // Use of acos() method
        // Value greater than 1, so passing NaN
        double Acosi = Math.acos(60);
        System.out.println("acos value of Acosi : "+Acosi);
        double x = Math.PI;

        // Use of toRadian() method
        x = Math.toRadians(x);
        double Acosj = Math.acos(x);
        System.out.println("acos value of Acosj : "+Acosj);
    }
}
```
**输出:**
```java
Initial value of int  : -1
Initial value of int  : 0.5
Absolute value of int : 1
Absolute value of int : 0.5

acos value of Acosi : NaN
acos value of Acosj : 1.5159376794536454
```

### 4. `addExact()`
`Math.addExact(int a, int b)` 方法返回传递的参数之和。

**特殊点:** 如果结果溢出一个 `int` 或 `long`（根据传递的参数），则方法抛出 `ArithmeticException`。

**语法:**
```java
public static int addExact(int x, int y)
                    or
public static long addExact(long x, long y)
```
**Parameters:**
`a` - first value
`b` - second value
**Returns:**
Sum of the specified method arguments - `a` and `b`.

### 5. `asin()`
`Math.asin()` 方法返回方法参数的反正弦值。返回的角度范围在 -π/2 到 π/2 之间。
反正弦是传递参数的反正弦。
`asin(arg) = sin⁻¹` of `arg`

**Special Case :**
*   如果参数为 NaN 或其绝对值大于 1，则结果为 NaN。
*   如果参数为零，则结果为零。

**语法:**
```java
public static double asin(double arg)
```
**Parameters:**
`arg` - argument passed.
**Returns:**
arc sine of the argument passed.

# Java Math 类常用方法详解

## cbrt()

`cbrt()` 方法返回传递参数的立方根。

**要点：**
*   如果参数是 `NaN`，结果也是 `NaN`。
*   如果参数是无限的，结果是一个与参数符号相同的无穷大。
*   如果参数为零，结果为零。

**语法：**
```java
public static double cbrt(double arg)
```
**参数：**
*   `arg` - 传递的参数。
**返回值：**
*   传递参数的立方根。

### 示例代码：在 Math 类中解释 addExact()、asin()、cbrt() 方法
```java
// Java program explaining Math class methods
// addExact(), asin(), cbrt()
import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        int a = 1, b = 8;

        // get the result of addExact method
        int radd = Math.addExact(a,b);
        System.out.println("Using addExact() : "+radd);
        System.out.println("");

        // Use of acos() method
        // Value greater than 1, so passing NaN
        double Asini = Math.asin(radd);
        System.out.println("asin value of Asini : "+Asini);
        double x = Math.PI;

        // Use of toRadian() method
        x = Math.toRadians(x);
        double Asinj = Math.asin(x);
        System.out.println("asin value of Asinj : "+Asinj);
        System.out.println("");

        // Use of cbrt() method
        double cbrtval = Math.cbrt(216);
        System.out.println("cube root : "+cbrtval);
    }
}
```
**输出：**
```
Using addExact() : 9

acos value of Asini : NaN
acos value of Asinj : 0.054858647341251204

cube root : 6.0
```

## floor()

`floor()` 方法返回参数的 floor 值，即小于或等于传递参数的最接近的整数值。
例如：101.23 的地板值 = 101。

**要点：**
如果传递了 `NaN` 或无限参数，则会产生相同的参数。

**语法：**
```java
public static double floor(double arg)
```
**参数：**
*   `arg` - 我们需要其 floor 值的参数。
**返回值：**
*   小于或等于传递参数的最接近的可能值。

## hypot()

`hypot(double p, double b)` 方法通过传递直角三角形的底和高作为参数，返回其斜边长度。
**斜边 = [高<sup>2</sup> + 底<sup>2</sup>]<sup>1/2</sup>**

**要点：**
*   如果任一参数为无穷大，则结果为正无穷大。
*   如果任一参数为 `NaN`，且任一参数都不是无穷大，则结果为 `NaN`。

**语法：**
```java
public static double hypot(double p, double b)
```
**参数：**
*   `p` - 直角三角形的高。
*   `b` - 直角三角形的底。
**返回值：**
*   直角三角形的斜边。

## IEEEremainder()

`IEEEremainder(double d1, double d2)` 方法通过对两个参数应用余数运算，返回符合 IEEE 754 标准的余数值。
余数 = **d1 – d2 * n**
其中，n = d1/d2。

**语法：**
```java
public static double IEEEremainder(double d1, double d2)
```
**参数：**
*   `d1` - 被除数。
*   `d2` - 除数。
**返回值：**
*   当被除数 (`d1`) 除以除数 (`d2`) 时的余数。

## log()

`log()` 方法返回传递参数的对数值。

**语法：**
```java
public static double log(double arg)
```
**参数：**
*   `arg` - 传递的参数。
**返回值：**
*   传递参数的对数值。

### 示例代码：在 Math 类中解释 floor()、hypot()、IEEEremainder()、log() 方法
```java
// Java program explaining MATH class methods
// floor(), hypot(), IEEEremainder(), log()
import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of floor method
        double f1 = 30.56, f2 = -56.34;
        f1 = Math.floor(f1);
        System.out.println("Floor value of f1 : "+f1);
        f2 = Math.floor(f2);
        System.out.println("Floor value of f2 : "+f2);
        System.out.println("");

        // Use of hypot() method
        double p = 12, b = -5;
        double h = Math.hypot(p, b);
        System.out.println("Hypotenuse : "+h);
        System.out.println("");

        // Use of IEEEremainder() method
        double d1 = 105, d2 = 2;
        double r = Math.IEEEremainder(d1,d2);
        System.out.println("Remainder : "+r);
        System.out.println("");

        // Use of log() method
        double l = 10;
        l = Math.log(l);
        System.out.println("Log value of 10 : "+l);
    }
}
```
**输出：**
```
Floor value of f1 : 30.0
Floor value of f2 : -57.0

Hypotenuse : 13.0

Remainder : 1.0

Log value of 10 : 2.302585092994046
```

[java.math 类及其方法|第 3 集](https://www.geeksforgeeks.org/java-math-class-methods-set-3/)

本文由 **莫希特·古普塔** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。