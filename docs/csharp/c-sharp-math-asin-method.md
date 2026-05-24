# C# |数学。Asin()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-asin-method/](https://www.geeksforgeeks.org/c-sharp-math-asin-method/)

***数学。Asin()*** 是一个内置的数学类方法，它返回正弦值作为双值参数给出的角度。如果论证是 *NaN* ，那么结果就是 **NaN** 。

**语法:**

```cs
public static double Asin(double num)

```

**参数:**

> **num:** 是表示正弦的数字，该参数的类型为*系统。双*。它必须大于或等于-1，但小于或等于 1。

**返回类型:**返回角度θ，以弧度为单位，类型为**系统。双**。这里，角度总是以弧度为单位进行测量，例如-π/2≤θ≤π/2。

**注意:**如果 num 的值大于 1 或小于-1 或等于 NaN，那么这个方法总是返回 NaN 作为结果。要将弧度(返回值)转换为度数*将其乘以 180 /数学。PI* 。正返回值始终代表与 x 轴的逆时针角度，负返回值始终代表顺时针角度。

**例:**

```cs
Input  : Math.Asin(2)
Output : NaN

Input  : Math.Asin(0.3584)
Output : 0.366553473829125

Input  : Math.Asin(0.0)
Output : 0

Input  : Math.Asin(-0.0)
Output : 0

Input  : Math.Asin(Double.PositiveInfinity)
Output : NaN

Input  : Math.Asin(Double.NegativeInfinity)
Output : NaN

```

**程序:**说明数学。Asin()方法

```cs
// C# program to demonstrate working
// of Math.Asin() method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        double a = Math.PI;

        // using Math.Asin() method
        Console.WriteLine(Math.Asin(a));

        // argument is greater than 1
        Console.WriteLine(Math.Asin(2));

        Console.WriteLine(Math.Asin(0.3584));

        double d = 0.0;
        double e = -0.0;
        double posi = Double.PositiveInfinity;
        double nega = Double.NegativeInfinity;
        double nan = Double.NaN;

        // Input positive zero
        // Output 0
        double res = Math.Asin(d);

        // converting to degree
        // i.e. output is 0 degree
        double rest = res * (180 / Math.PI);
        Console.WriteLine(rest);

        // Input negative zero
        // Output 0
        Console.WriteLine(Math.Asin(e));

        // input PositiveInfinity
        // Output NaN
        Console.WriteLine(Math.Asin(posi));

        // input NegativeInfinity
        // Output NaN
        Console.WriteLine(Math.Asin(nega));

        // input NaN
        // Output NaN
        Console.WriteLine(Math.Asin(nan));
    }
}
```

**输出:**

```cs
NaN
NaN
0.366553473829125
0
0
NaN
NaN
NaN

```

**参考:**T2】https://msdn.microsoft.com/en-us/library/system.math.Asin