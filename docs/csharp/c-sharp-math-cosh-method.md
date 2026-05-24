# C# |数学。Cosh()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-math-cosh-method/](https://www.geeksforgeeks.org/c-sharp-math-cosh-method/)

***数学。Cosh()*** 是一个内置的数学类方法，它返回给定双值参数的双曲余弦值。
**语法:**

```cs
public static double Cosh(double num)
```

**参数:**

> **num:** 是要返回双曲 cos 的数字，该参数的类型为*系统。双*。

**返回值:**该方法返回类型为*系统的数值的双曲余弦值。双*。如果 num 等于否定有限性或肯定有限性，则返回肯定有限性。如果 num 等于 NaN，则返回 NaN。
**例:**

```cs
Input   : 60.0
Output  : 5.71003694907842E+25
```

下面的程序说明了数学。Cosh 方法:
**程序 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Math.Cosh()
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        double num1 = 60.0, num2 = 0.0, num3 = 1.0;

        // It returns the hyperbolic cosine of
        // specified angle in radian
        double coshvalue = Math.Cosh(num1);
        Console.WriteLine("The cosh of num1 = " + coshvalue);

        coshvalue = Math.Cosh(num2);
        Console.WriteLine("The cosh of num2 = " + coshvalue);

        coshvalue = Math.Cosh(num3);
        Console.WriteLine("The cosh of num3 = " + coshvalue);
    }
}
```

**Output:** 

```cs
The cosh of num1 = 5.71003694907842E+25
The cosh of num2 = 1
The cosh of num3 = 1.54308063481524
```

**节目 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Math.Cosh() Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        double num1 = (30 * (Math.PI)) / 180, num2 = 11.0, num3 = 45.0;

        // It returns the hyperbolic cosine of
        // angle in radian
        double coshvalue = Math.Cosh(num1);
        Console.WriteLine("The cosh of num1 = " + coshvalue);

        coshvalue = Math.Cosh(num2);
        Console.WriteLine("The cosh of num2 = " + coshvalue);

        coshvalue = Math.Cosh(num3);
        Console.WriteLine("The cosh of num3 = " + coshvalue);
    }
}
```

**Output:** 

```cs
The cosh of num1 = 1.14023832107643
The cosh of num2 = 29937.0708659498
The cosh of num3 = 1.74671355287425E+19
```