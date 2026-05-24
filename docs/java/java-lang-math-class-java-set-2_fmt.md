# Java.lang.Math 类 Java |第 2 集

> 原文: [https://www.geeksforgeeks.org/java-lang-math-class-java-set-2/](https://www.geeksforgeeks.org/java-lang-math-class-java-set-2/)

[Java.lang.Math 类 Java |第 1 集](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/)

## 更多方法

### 13. `cosh()`
`java.lang.Math.cosh()` 方法返回传入参数的双曲余弦值。
**特殊案例：**
*   如果参数是 `NaN`，结果是 `NaN`。
*   如果参数为零，则结果为 `1.0`。
*   如果参数为无穷大，则结果为正无穷大。

**语法：**
```java
public static double cosh(double arg)
```
**参数：**
`arg` - 要返回其双曲余弦值的数字。
**返回：**
参数 `arg` 的双曲余弦值。

### 14. `decrementExact()`
`java.lang.Math.decrementExact()` 方法将传入的参数值减 1。
**语法：**
```java
public static int decrementExact(int arg)
// 或
public static long decrementExact(long arg)
```
**参数：**
`arg` - 传入的参数。
**返回：**
参数减一后的值。
**抛出：**
如果结果根据参数数据类型溢出 `long` 或 `int` 数据类型，则抛出异常。

### 15. `exp()`
`java.lang.Math.exp(double arg)` 方法返回欧拉数 e 的 double 参数次幂。
**重要案例：**
*   如果参数是 `NaN`，结果是 `NaN`。
*   如果参数为正无穷大，则结果为正无穷大。
*   如果参数为负无穷大，则结果为正零。

**语法：**
```java
public static double exp(double arg)
```
**参数：**
`arg` - 传入的参数。
**返回：**
欧拉数 e 的传入参数次幂。

**Java 代码，解释 `lang.Math` 类中的 `exp()`、`decrementExact()`、`cosh()` 方法。**
```java
// Java program explaining lang.Math class methods
// exp(), decrementExact(), cosh()

import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of cosh() method
        double value = 2;
        double coshValue = Math.cosh(value);
        System.out.println("Hyperbolic Cosine of "  + coshValue);
        System.out.println("");

        // Use of decrementExact() method
        int result = Math.decrementExact(3051);
        System.out.println("Use of decrementExact() : " + result);
        System.out.println("");

        // Use of exp() method
        // declare the exponent to be used
        double exponent = 34;
        // raise e to exponent declared
        double expVal = Math.exp(exponent);
        System.out.println("Value of exp : "+ expVal);
    }
}
```
**输出：**
```java
Using addExact() : 9

acos value of Asini : NaN
acos value of Asinj : 0.054858647341251204

cube root : 6.0
```

### 16. `incrementExact()`
`java.lang.Math.incrementExact()` 方法通过增加参数的值来返回参数。
**语法：**
```java
public static int incrementExact(int arg)
// 或
public static long incrementExact(long arg)
```
**参数：**
`arg` - 参数。
**返回：**
参数递增后的值。

### 17. `log10()`
`java.lang.Math.log10()` 方法返回传入参数的以 10 为底的对数值。
**语法：**
```java
public static double log(double arg)
```
**参数：**
`arg` - 传入的参数。
**返回：**
传入参数的以 10 为底的对数值。

### 18. `pow()`
`java.lang.Math.pow(double b, double e)` 方法返回 `b` 的 `e` 次幂的值。
**语法：**
```java
public static double pow(double b, double e)
```
**参数：**
`b` - 底数。
`e` - 指数。
**返回：**
底数 `b` 的指数 `e` 次幂的值。

**Java 代码，解释 `lang.Math` 类中的 `incrementExact()`、`log10()`、`pow()` 方法。**
```java
// Java program explaining lang.MATH class methods
// incrementExact(), log10(), pow()

import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of incrementExact() method
        int f1 = 30, f2 = -56;
        f1 = Math.incrementExact(f1);
        System.out.println("Incremented value of f1 : "+f1);

        f2 = Math.incrementExact(f2);
        System.out.println("Incremented value of f2 : "+f2);
        System.out.println("");

        // Use of log10() method
        double value = 10;
        double logValue = Math.log10(value);
        System.out.println("Log10 value of 10 : "+logValue);
        System.out.println("");

        // Use of pow() method
        double b = 10, e = 2;
        double power = Math.pow(b,e);
        System.out.println("Use of pow() : "+power);
    }
}
```
**输出：**
```java
Incremented value of f1 : 31
Incremented value of f2 : -55

Log10 value of 10 : 1.0

Use of pow() : 100.0
```

### 19. `signum()`
`java.lang.Math.signum()` 方法返回传入参数的符号函数值。
```
signum fun(x) = -1    if x < 0
                 0    if x = 0
                 1    if x > 0
```
**语法：**
```java
public static double signum(double x)
// 或
public static float signum(float x)
```
**参数：**
`x` - 我们需要其符号函数值的参数。
**返回：**
`x` 的符号函数值。

### 20. `round()`
`java.lang.Math.round()` 方法将传入的参数四舍五入到最接近的整数。
**注：** 如果参数为 `NaN`，结果为 0。
**语法：**
```java
public static long round(long arg)
// 或
public static double round(double arg)
```
**参数：**
`arg` - 需要四舍五入的参数。
**返回：**
参数四舍五入后的值。

### 21. `max()`
`java.lang.Math.max(double v1, double v2)` 方法返回两个传入参数值中较大的一个。
此方法仅使用数值大小进行比较，不考虑符号。
**语法：**
```java
public static double max(double v1, double v2)
```
**参数：**
`v1` - 第一个值。
`v2` - 第二个值。
**返回：**
`v1` 或 `v2`，取决于哪个数字更大。如果 `v1 = v2`，则可以返回两者中的任意一个。

**Java 代码解释 `lang.Math` 类中的 `signum()`、`round()`、`max()` 方法。**
```java
// Java code explaining the lang.Math Class methods
// signum(), round(), max()

import java.lang.*;
public class NewClass
{
    public static void main(String args[])
    {
        // Use of signum() method
        double x = 10.4556, y = -23.34789;
        double signm = Math.signum(x);
        System.out.println("Signum of 10.45  = "+signm);

        signm = Math.signum(y);
        System.out.println("Signum of -23.34 = "+signm);
        System.out.println("");

        // Use of round() method
        double r1 = Math.round(x);
        System.out.println("Round off 10.4556  = "+r1);

        double r2 = Math.round(y);
        System.out.println("Round off 23.34789 = "+r2);
        System.out.println("");

        // Use of max() method on r1 and r2
        double m = Math.max(r1, r2);
        System.out.println("Max b/w r1 and r2 = "+r2);
    }
}
```
**输出：**
```java
Signum of 10.45  = 1.0
Signum of -23.34 = -1.0

Round off 10.4556  = 10.0
Round off 23.34789 = -23.0

Max b/w r1 and r2 = -23.0
```

### 22. `log1p()`
`java.lang.Math.log1p()` 方法返回 `(传入参数 + 1)` 的自然对数。
**语法：**
```java
public static double log1p(double arg)
```
**参数：**
`arg` - 参数。
**返回：**
`(参数 + 1)` 的对数。此结果在精确结果的最后一位单位内。

### 23. `ulp()`
`java.lang.Math.ulp()` 方法返回**最小精度单位 (ulp)**，即两个浮点数之间的最小距离。
这里，它是参数与下一个较大值之间的最小距离。
**语法：**
```java
public static double ulp(double arg)
// 或
public static float ulp(float arg)
```
**参数：**
`arg` - 传入的参数。
**返回：**
参数与下一个较大值之间的最小距离。

**Java 代码，解释 `lang.Math` 类中的 `ulp()`、`log1p()` 方法。**
```java
// Java code explaining the lang.Math Class methods
// ulp(), log1p()
```

## Java Math 类方法示例

```java
import java.lang.*;

public class NewClass {
    public static void main(String args[]) {
        // Use of ulp() method
        double x = 34.652, y = -23.34789;
        double u = Math.ulp(x);
        System.out.println("ulp of 34.652    : " + u);

        u = Math.ulp(y);
        System.out.println("ulp of -23.34789 : " + u);
        System.out.println("");

        // Use of log() method
        double l = 99;
        double l1 = Math.log1p(l);
        System.out.println("Log of (1 + 99)  : " + l1);

        l1 = Math.log(100);
        System.out.println("Log of 100       : " + l1);
    }
}
```

**输出:**

```
ulp of 34.652    : 7.105427357601002E-15
ulp of -23.34789 : 3.552713678800501E-15

Log of (1 + 99)  : 4.605170185988092
Log of 100       : 4.605170185988092
```

本文由 [<font color="green">**莫希特·古普塔 _OMG 供稿😀**</font>](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论..