# C# |数学。Atan()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-atan-method/](https://www.geeksforgeeks.org/c-sharp-math-atan-method/)

***数学。Atan()*** 是一个内置的数学类方法，它返回其切线作为双值参数给出的角度。如果论证是 *NaN* ，那么结果就是 **NaN** 。

**语法:**

```cs
public static double Atan(double num)

```

**参数:**

> **num:** 是表示切线的数字，该参数的类型为*系统。双*。

**返回类型:**返回角度θ，以弧度为单位，类型为**系统。双**。这里，角度总是以弧度为单位进行测量，例如-π/2≤θ≤π/2。

**例:**

```cs
Input  : Math.Atan(1)
Output : 0.785398163397448

Input  : Math.Atan(0.0)
Output : 0

Input  : Math.Atan(-0.0)
Output : 0

Input  : Math.Atan(Double.PositiveInfinity)
Output : 1.5707963267949

Input  : Math.Atan(Double.NegativeInfinity)
Output : -1.5707963267949

```

**程序:**说明数学。阿坦()法

```cs
// C# program to demonstrate working
// of Math.Atan() method
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {
        double a = Math.PI;

        // using Math.Atan() method 
        Console.WriteLine(Math.Atan(a));

        double d = 0.0;
        double e = -0.0;
        double posi = Double.PositiveInfinity;
        double nega = Double.NegativeInfinity;
        double nan = Double.NaN;

        Console.WriteLine(Math.Atan(1));

        // Input positive zero
        // Output positive zero
        Console.WriteLine(Math.Atan(d));

        // Input negative zero
        // Output positive zero
        Console.WriteLine(Math.Atan(e));

        // input PositiveInfinity
        // Output 1.5707963267949
        Console.WriteLine(Math.Atan(posi));

        // input NegativeInfinity
        // Output -1.5707963267949
        Console.WriteLine(Math.Atan(nega));

        // input NaN
        // Output NaN
        Console.WriteLine(Math.Atan(nan));
    }
}
```

T5】输出:

```cs
1.26262725567891
0.785398163397448
0
0
1.5707963267949
-1.5707963267949
NaN

```

**参考:**T2】https://msdn.microsoft.com/en-us/library/system.math.atan