# C# |数学。Log10()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-log10-method/](https://www.geeksforgeeks.org/c-sharp-math-log10-method/)

在 C# 中 ***数学。*log10()**是一种数学类方法。它用于返回指定数字的以 10 为底的对数。

**语法:**

```cs
public static double Log10(double val)
```

**参数:**

> **val:** 是要计算对数的指定数字，类型为*系统。双*。

**返回值:**返回*值*的对数(以*值*的 10 个对数为基数)，类型为*系统。双*。

**注意:**参数*值*始终指定为基数 10。返回值取决于传递的参数。以下是一些情况:

*   If the parameter is *plus* , then the method will return the natural logarithm or **logarithm <sub>10</sub> (val)** .
*   If the parameter is *zero* , the result is *negative finite* .
*   If the independent variable is *negative (less than zero)* or equal to *nan* , the result is *nan* .
*   If the parameter is *positive definite* , the result is *positive definite* .
*   If the independent variable is *negative infinity* , then the result is *nan* .

**例:**

```cs
// C# program to demonstrate working
// of Math.Log10(Double) method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // double values whose logarithm 
        // to be calculated
        double a = 4.55;
        double b = 0;
        double c = -2.45;
        double nan = Double.NaN;
        double positiveInfinity = Double.PositiveInfinity;     
        double negativeInfinity = Double.NegativeInfinity;

        // Input is positive number so output
        // will be logarithm of number
        Console.WriteLine(Math.Log10(a));

        // positive zero as argument, so output 
        // will be -Infinity
        Console.WriteLine(Math.Log10(b));

        // Input is negative number so output
        // will be NaN
        Console.WriteLine(Math.Log10(c));

        // Input is NaN so output
        // will be NaN
        Console.WriteLine(Math.Log10(nan));

        // Input is PositiveInfinity so output
        // will be Infinity
        Console.WriteLine(Math.Log10(positiveInfinity));

        // Input is NegativeInfinity so output
        // will be NaN
        Console.WriteLine(Math.Log10(negativeInfinity));
    }
}
```

**输出:**

```cs
0.658011396657112
-Infinity
NaN
NaN
Infinity
NaN

```

**参考:**[https://msdn . Microsoft . com/en-us/library/system . math . log 10(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/system.math.log10(v=vs.110).aspx)