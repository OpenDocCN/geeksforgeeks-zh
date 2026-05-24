# Java.lang.Math 类

> 原文: [https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/)

`Math`类方法有助于执行数值运算，如平方、平方根、立方、立方根、指数和三角运算。

**声明：**

```java
public final class Math extends Object
```

**什么是 `NaN` 参数？**
一个持有`double`类型`NaN`（非数字）值的常量。它相当于`Double.longBitsToDouble(0x7ff8000000000001L)`返回的值。

## 方法详解

### 1. `abs()`
`java.lang.Math.abs()`方法返回传递的任何类型参数的绝对值。这个方法可以处理所有的数据类型。

*   如果参数为正零或负零，则结果为正零。
*   如果参数为无穷大，则结果为正无穷大。
*   如果传递的参数是`NaN`，则结果是`NaN`。

**语法：**

```java
public static datatype abs(datatype arg)
```

**参数：**
`arg` - 需要计算其绝对值的参数。

**返回值：**
传递参数的绝对值。

### 2. `acos()`
`java.lang.Math.acos()`方法返回传递的参数的反余弦值。
反余弦是传递参数的余弦的逆运算。
`acos(arg) = cos⁻¹(arg)`

**特例：** 如果自变量为`NaN`或其绝对值大于 1，结果为`NaN`。

**语法：**

```java
public static double acos(double a)
```

**参数：**
`a` - 需要计算其反余弦值的参数（以弧度为单位）。

**返回值：**
参数的反余弦值。

### 3. `toRadians()`
`java.lang.Math.toRadians(double deg)`方法将参数（度数）转换为弧度。
**注意：** `Math`类通常以弧度作为输入，这在现实应用中非常不同，因为角度通常以度数表示。

**语法：**

```java
public static double toRadians(double deg)
```

**参数：**
`deg` - 需要转换为弧度的角度（度）。

**返回值：**
度数参数对应的弧度值。

### 4. `asin()`
`java.lang.Math.asin()`方法返回传递参数的反正弦值。返回的角度在`-π/2`到`π/2`的范围内。
反正弦是传递参数的正弦的逆运算。
`asin(arg) = sin⁻¹(arg)`

**特殊情况：**

*   如果参数为`NaN`或其绝对值大于 1，则结果为`NaN`。
*   如果参数为零，则结果为零。

**语法：**

```java
public static double asin(double arg)
```

**参数：**
`arg` - 传递的参数。

**返回值：**
传递参数的反正弦值。

### 5. `cbrt()`
`java.lang.Math.cbrt()`方法返回传递参数的立方根。

**特别提示：**

*   如果参数是`NaN`，则结果是`NaN`。
*   如果参数是无限的，则结果是一个与参数符号相同的无穷大。
*   如果参数为零，则结果为零。

**语法：**

```java
public static double cbrt(double arg)
```

**参数：**
`arg` - 传递的参数。

**返回值：**
传递参数的立方根。

### 6. `floor()`
`java.lang.Math.floor()`方法返回参数的`floor`值，即小于或等于传递参数的最接近的整数值。
例：`floor(101.23)` = `101.0`

**重要提示：** 如果传递了`NaN`或无限参数，会产生相同的参数。

**语法：**

```java
public static double floor(double arg)
```

**参数：**
`arg` - 需要计算其`floor`值的参数。

**返回值：**
小于或等于参数的最接近的可能值（数学整数）。

### 7. `hypot()`
`java.lang.Math.hypot(double p, double b)`方法返回直角三角形的斜边，给定底边和垂直边作为参数。
**斜边 = (垂直² + 底边²)^(1/2)**

**要点：**

*   如果任一参数为无穷大，则结果为正无穷大。
*   如果任一参数为`NaN`，且任一参数都不是无穷大，则结果为`NaN`。

**语法：**

```java
public static double hypot(double p, double b)
```

**参数：**
`p` - 直角三角形的垂直边。
`b` - 直角三角形的底边。

**返回值：**
直角三角形的斜边。

### 8. `IEEEremainder()`
`java.lang.Math.IEEEremainder(double d1, double d2)`方法通过对两个参数应用余数运算，根据 IEEE 754 标准返回余数值。
余值 = `d1 – d2 * n`
其中，`n` = `d1/d2` 的最接近精确值。

**语法：**

```java
public static double IEEEremainder(double d1, double d2)
```

**参数：**
`d1` - 被除数。
`d2` - 除数。

**返回值：**
被除数 (`d1`) 除以除数 (`d2`) 后的余数。

### 9. `log()`
`java.lang.Math.log()`方法返回传递参数的自然对数值（以`e`为底）。

**语法：**

```java
public static double log(double arg)
```

**参数：**
`arg` - 传递的参数。

**返回值：**
传递参数的对数值。

### 10. `ceil()`
`java.lang.Math.ceil(double a)`方法返回一个可能的最小值，该值大于或等于传递的参数。返回值是一个数学整数。

*   如果返回值已经是数学整数，则结果相同。
*   如果传递的参数是`NaN`、无穷大或零，则结果相同。
*   如果传递的参数小于零但大于`-1.0`，则结果为负零。

**语法：**

```java
public static double ceil(double arg)
```

**参数：**
`arg` - 参数值。

**返回值：**
大于或等于参数的最小可能值（数学整数）。

### 11. `atan()`
`java.lang.Math.atan()`方法返回参数值的反正切。返回的角度在`-π/2`到`π/2`的范围内。
反正切是传递参数的正切的逆运算。
`atan(arg) = tan⁻¹(arg)`

**特殊情况：**

*   如果传递的参数是`NaN`或其绝对值大于 1，则结果是`NaN`。
*   如果参数为零，则结果为零。

**语法：**

```java
public static double atan(double a)
```

**参数：**
`a` - 需要计算其反正切值的参数（以弧度为单位）。

**返回值：**
参数的反正切值。

### 12. `copySign()`
`java.lang.Math.copySign()`方法返回第一个浮点参数，但带有第二个参数的符号。

**语法：**

```java
public static double copySign(double m, double s)
public static float copySign(float m, float s)
```

**参数：**
`m` - 数值（幅度）。
`s` - 符号。

**返回值：**
带有第二个参数符号的第一个参数。

## 代码示例

### 示例 1：`abs()`、`acos()`、`toRadians()` 方法

```java
// Java program explaining lang.Math class methods
// abs(), acos(), toRadians()

import java.lang.*;
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

**输出：**

```java
Initial value of int  : -1
Initial value of int  : 0.5
Absolute value of int : 1
Absolute value of int : 0.5

acos value of Acosi : NaN
acos value of Acosj : 1.5159376794536454
```

### 示例 2：`asin()`、`cbrt()` 方法

```java
// Java program explaining lang.Math class methods
// asin(), cbrt()

import java.lang.*;
public class NewClass
{

    public static void main(String[] args)
    {
        int a = 1, b = 8;
        int radd = a+b;

        // Use of asin() method
        // Value greater than 1, so passing NaN
        double Asini = Math.asin(radd);
        System.out.println("asin value of Asini : " + Asini);
        double x = Math.PI;

        // Use of toRadian() method
        x = Math.toRadians(x);
        double Asinj = Math.asin(x);
        System.out.println("asin value of Asinj : " + Asinj);
        System.out.println("");

        // Use of cbrt() method
        double cbrtval = Math.cbrt(216);
        System.out.println("cube root : " + cbrtval);

    }
}
```

**输出：**

```java
asin value of Asini : NaN
asin value of Asinj : 0.054858647341251204

cube root : 6.0
```

### 示例 3：`floor()`、`hypot()`、`IEEEremainder()`、`log()` 方法

```java
// Java program explaining lang.MATH class methods
// floor(), hypot(), IEEEremainder(), log()

import java.lang.*;
public class NewClass
{

    public static void main(String[] args)
    {
        // Use of floor method
        double f1 = 30.56, f2 = -56.34;
        f1 =Math.floor(f1);
        System.out.println("Floor value of f1 : "+f1);

        f2 =Math.floor(f2);
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

```java
Floor value of f1 : 30.0
Floor value of f2 : -57.0

Hypotenuse : 13.0

Remainder : 1.0

Log value of 10 : 2.302585092994046
```

## Java Math 类方法示例

```java
// Java program explaining lang.Math class methods
// atan(), ceil(), copySign()

import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of atan() method
        double Atani = Math.atan(0);
        System.out.println("atan value of Atani : "+Atani);
        double x = Math.PI/2;

        // Use of toRadian() method
        x = Math.toRadians(x);
        double Atanj = Math.atan(x);
        System.out.println("atan value of Atanj : "+Atanj);
        System.out.println("");

        // Use of ceil() method
        double val = 15.34 ,ceilval;
        ceilval = Math.ceil(val);
        System.out.println("ceil value of val : "+ceilval);
        System.out.println("");

        double dblMag = val;
        double dblSign1 = 3;
        double dblSign2 = -3;

        // Use of copySign() method
        double result1 = Math.copySign(dblMag,dblSign1);
        System.out.println("copySign1 : "+result1);

        double result2 = Math.copySign(dblMag,dblSign2);
        System.out.println("copySign2 : "+result2);

    }
}
```

`输出:`

```java
atan value of Atani : 0.0
atan value of Atanj : 0.0274087022410345

ceil value of val : 16.0

copySign1 : 15.34
copySign2 : -15.34
```

`下一篇` : [Java.lang.math |第二集](https://www.geeksforgeeks.org/java-lang-math-class-java-set-2/)

本文由 [`Mohit Gupta_OMG 供稿😀`](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。