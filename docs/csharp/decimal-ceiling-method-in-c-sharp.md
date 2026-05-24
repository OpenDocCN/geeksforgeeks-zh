# 小数。C# 中的天花板()方法

> 原文:[https://www . geesforgeks . org/decimal-天花板-c-sharp 中的方法/](https://www.geeksforgeeks.org/decimal-ceiling-method-in-c-sharp/)

此方法用于将小数舍入到最接近正无穷大的整数。

> **语法:**公共静态小数上限(小数 d)；
> 这里 **d** 是要计算其上限值的小数。
> 
> **返回值:**返回大于或等于 *d* 参数的最小整数值。请注意，此方法返回一个十进制数而不是整数类型。

下面的程序说明了*小数的使用。上限(十进制)法*:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.Ceiling(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = 4.01m;

        // finding the ceiling of 
        // the Decimal value
        // using ceiling() method;
        Decimal value = Decimal.Ceiling(a);

        // Display the ceiling
        Console.WriteLine("Ceiling Value is : {0}",
                                            value);
    }
}
```

**Output:**

```cs
Ceiling Value is : 5

```

**例 2:**

```cs
// C# program to demonstrate the
// Decimal.Ceiling(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = -5.03m;

        // finding the Ceiling of
        // the Decimal value
        // using Ceiling() method;
        Decimal value = Decimal.Ceiling(a);

        // Display the Ceiling
        Console.WriteLine("Ceiling Value is : {0}",
                                            value);
    }
}
```

**Output:**

```cs
Ceiling Value is : -5

```

**例 3:**

```cs
// C# program to demonstrate the
// Decimal.Ceiling(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = 2.00m;

        // finding the Ceiling of
        // the Decimal value
        // using Ceiling() method;
        Decimal value = Decimal.Ceiling(a);

        // Display the Ceiling
        Console.WriteLine("Ceiling Value is : {0}",
                                            value);
    }
}
```

**Output:**

```cs
Ceiling Value is : 2

```