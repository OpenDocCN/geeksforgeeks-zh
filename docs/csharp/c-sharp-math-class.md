# C# |数学类

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-class/](https://www.geeksforgeeks.org/c-sharp-math-class/)

在 C# 中，**数学类**属于系统命名空间。它用于为对数函数、三角函数和其他有用的数学函数提供静态方法和常数。它是一个静态类，继承了对象类。

```cs
public static class Math
```

#### 菲尔茨

字段是在类或结构中声明的变量。这些被认为是其包含类型的成员。字段可以是静态字段或实例字段。数学类包含两个字段，即 *E* 和 *PI* 。

1.  **数学。e 字段:**该字段表示自然对数基数，由常数 e 指定
2.  **数学。π场:**它表示圆的周长与直径的比值，由常数π(π)指定。

**示例:**

```cs
// C# program to demonstrate the
// value of Math Class Fields
using System;

class GFG {

    // Main method
    static void Main()
    {

        // To find E constant values
        double e = Math.E;

        // Print result
        Console.WriteLine("Math.E = " + e);

        // To find PI constant values
        double pi_value = Math.PI;

        // Print result
        Console.WriteLine("Math.PI = " + pi_value);
    }
}
```

**输出:**

```cs
Math.E = 2.71828182845905
Math.PI = 3.14159265358979

```

可以从 [**C# |数学类字段带例题**](https://www.geeksforgeeks.org/c-math-class-fields-with-examples/) 阅读更多关于字段的内容。

#### 方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| **[【Abs()](https://www.geeksforgeeks.org/c-math-abs-method-set-1/)** | 返回指定数字的绝对值。 |
| **[【acos()](https://www.geeksforgeeks.org/c-math-acos-method/)** | 返回余弦值为指定数字的角度。 |
| **Acosh()** | 返回指定数字的反双曲余弦值。 |
| **[阿辛()](https://www.geeksforgeeks.org/c-math-asin-method/)** | 返回正弦值为指定数字的角度。 |
| 就为了使用一个同样的描述法 | 返回指定数字的反双曲正弦值。 |
| **[【atan()](https://www.geeksforgeeks.org/c-math-atan-method/)** | 返回切线为指定数值的角度。 |
| **[【atan2()](https://www.geeksforgeeks.org/c-math-atan2-method/)** | 返回正切为两个指定数字的商的角度。 |
| **阿坦()** | 返回指定数字的反双曲正切值。 |
| **[【big mul()](https://www.geeksforgeeks.org/c-math-bigmul-method/)** | 产生两个 32 位数字的乘积。 |
| **Cbrt()** | 返回指定值的立方根。 |
| **[【天花板()](https://www.geeksforgeeks.org/c-math-ceiling-method/)** | 返回大于或等于指定数字的最小整数值。 |
| **夹钳()** | 它用于将值限制在给定的范围内。 |
| **[Cos()](https://www.geeksforgeeks.org/c-math-cos-method/)** | 返回指定角度的余弦值。 |
| **[【Cosh()](https://www.geeksforgeeks.org/c-math-cosh-method/)** | 返回指定角度的双曲余弦值。 |
| **[吃()](https://www.geeksforgeeks.org/c-math-divrem-method/)** | 计算两个数的商，并在输出参数中返回余数。 |
| **[【Exp()](https://www.geeksforgeeks.org/c-math-exp-method/)** | 返回 e 的指定幂。 |
| **[【楼层()](https://www.geeksforgeeks.org/c-math-floor-method/)** | 返回小于或等于指定数字的最大整数值。 |
| **[【ieeere main()](https://www.geeksforgeeks.org/c-math-ieeeremainder-method/)** | 返回一个指定数除以另一个指定数所得的余数。 |
| **[【Log()](https://www.geeksforgeeks.org/c-math-log-method/)** | 返回指定数字的对数。 |
| **[Log10()](https://www.geeksforgeeks.org/c-math-log10-method/)** | 返回指定数字的以 10 为底的对数。 |
| **[【Max()](https://www.geeksforgeeks.org/c-math-max-method/)** | 返回两个指定数字中较大的一个。 |
| **[Min()](https://www.geeksforgeeks.org/c-math-min-method/)** | 返回两个数字中较小的一个。 |
| **[【Pow()](https://www.geeksforgeeks.org/c-math-pow-method/)** | 返回提升到指定幂的指定数字。 |
| **[【回合()](https://www.geeksforgeeks.org/c-math-round-method-set-1/)** | 将值舍入到最接近的整数或指定的小数位数。 |
| **[标志()](https://www.geeksforgeeks.org/c-math-sign-method/)** | 返回一个指示数字符号的整数。 |
| **[【Sin()](https://www.geeksforgeeks.org/c-math-sin-method/)** | 返回指定角度的正弦值。 |
| **[辛赫()](https://www.geeksforgeeks.org/c-math-sinh-method/)** | 返回指定角度的双曲正弦值。 |
| **[【sqrt()](https://www.geeksforgeeks.org/c-math-sqrt-method/)** | 返回指定数字的平方根。 |
| **[【谭()](https://www.geeksforgeeks.org/c-math-tan-method/)** | 返回指定角度的切线。 |
| **[【Tanh()](https://www.geeksforgeeks.org/c-math-tanh-method/)** | 返回指定角度的双曲正切值。 |
| **[截断()](https://www.geeksforgeeks.org/c-math-truncate-method/)** | 计算数字的整数部分。 |

</figure>

**示例:**

```cs
// C# program to illustrate the
// Math class methods
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // using Floor() Method
        Console.WriteLine("Floor value of 123.123: "
                             + Math.Floor(123.123));

        // using Asin() Method
        Console.WriteLine("Asin value of 0.35: "
                             + Math.Asin(0.35));

        // using Sqrt() Method
        Console.WriteLine("Square Root of 81: "
                              + Math.Sqrt(81));

        // using Round() Method
        Console.WriteLine("Round value of 14.6534: "
                             + Math.Round(14.6534));
    }
}
```

**输出:**

```cs
Floor value of 123.123: 123
Asin value of 0.35: 0.35757110364551
Square Root of 81: 9
Round value of 14.6534: 15

```