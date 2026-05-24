# C# |数学。Acos()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-acos-method/](https://www.geeksforgeeks.org/c-sharp-math-acos-method/)

***数学。Acos()*** 是一个内置的数学类方法，它返回余弦值为双值参数的角度。如果论证是 *NaN* ，那么结果就是 **NaN** 。

**语法:**

```cs
public static double Acos(double num)

```

**参数:**

> **num:** 是表示余弦的数字，该参数的类型为*系统。双*。必须是*大于等于-1* ，但*小于等于 1* 。

**返回类型:**返回角度θ，以弧度为单位，类型为**系统。双**。这里的角度总是以弧度来度量的，比如 0≤θ≤π。

**注意:**如果 num 的值大于 1 或小于-1 或等于 *NaN* ，则该方法始终返回 *NaN* 作为结果。要将弧度(返回值)转换为度数*将其乘以 180 /数学。PI* 。

**例:**

```cs
Input  : Math.Acos(2)
Output : NaN

Input  : Math.Acos(0.3584)
Output : 1.20424285296577

Input  : Math.Acos(0.0)
Output : 1.5707963267949

Input  : Math.Acos(-0.0)
Output : 1.5707963267949

Input  : Math.Acos(Double.PositiveInfinity)
Output : NaN

Input  : Math.Acos(Double.NegativeInfinity)
Output : NaN

```

**程序:**说明数学。Acos()方法

```cs
// C# program to demonstrate working
// of Math.Acos() method
using System;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {
        double a = Math.PI;

        // using Math.Acos() method
        Console.WriteLine(Math.Acos(a));

        // argument is greater than 1
        Console.WriteLine(Math.Acos(2));

        Console.WriteLine(Math.Acos(0.3584));

        double d = 0.0;
        double e = -0.0;
        double posi = Double.PositiveInfinity;
        double nega = Double.NegativeInfinity;
        double nan = Double.NaN;

        // Input positive zero
        // Output 1.5707963267949
        double res = Math.Acos(d);

        // converting to degree
        // i.e output will be 90 degree
        double rest = res * (180 / Math.PI);
        Console.WriteLine(rest);

        // Input negative zero
        // Output 1.5707963267949
        Console.WriteLine(Math.Acos(e));

        // input PositiveInfinity
        // Output NaN
        Console.WriteLine(Math.Acos(posi));

        // input NegativeInfinity
        // Output NaN
        Console.WriteLine(Math.Acos(nega));

        // input NaN
        // Output NaN
        Console.WriteLine(Math.Acos(nan));
    }
}
```

**输出:**

```cs
NaN
NaN
1.20424285296577
90
1.5707963267949
NaN
NaN
NaN

```

**参考:**T2】https://msdn.microsoft.com/en-us/library/system.math.Acos