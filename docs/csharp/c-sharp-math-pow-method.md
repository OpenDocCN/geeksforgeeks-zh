# C# |数学。Pow()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-pow-method/](https://www.geeksforgeeks.org/c-sharp-math-pow-method/)

在 C# 中 ***数学。*pow()**是一种数学类方法。这种方法用来计算一个数与另一个数的幂的乘积。

**语法:**

```cs
public static double Pow(double base, double power)

```

**参数:**

> **双基:**是一个要加幂的双精度浮点数，这个参数的类型是*系统。双*。
> 
> **二次幂:**是一个双精度浮点数，指定一个幂或指数，这个参数的类型是*系统。双*。

**返回类型:**函数返回升到幂的基数。这种方法的类型是*系统。双*

**示例:**

```cs
Input  : base = 8, power =2 
Output : 64

Input  : base = 2.5, power =3
Output : 15.625

```

**程序:**演示数学。Pow()

```cs
// C# program to illustrate the 
// Math.Pow() function
using System;
class GFG {

    // Main Method
    static public void Main()
    {

        // Find power using Math.Pow
        // 6 is base and 2 is power or
        // index or exponent of a number
        double pow_ab = Math.Pow(6, 2);

        // Print the result
        Console.WriteLine(pow_ab);

        // 3.5 is base and 3 is power or
        // index or exponent of a number
        double pow_tt = Math.Pow(3.5, 3);

        // Print the result
        Console.WriteLine(pow_tt);

        // 202 is base and 4 is power or
        // index or exponent of a number
        double pow_t = Math.Pow(202, 4);

        // Print the result
        Console.WriteLine(pow_t);
    }
}
```

**输出:**

```cs
36
42.875
1664966416

```

**参考:**[https://msdn . Microsoft . com/en-us/library/system . math . pow(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/system.math.pow(v=vs.110).aspx)