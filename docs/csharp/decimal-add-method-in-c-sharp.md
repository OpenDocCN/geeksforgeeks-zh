# 小数。在 C# 中添加()方法

> 原文:[https://www . geesforgeks . org/decimal-add-method in-c-sharp/](https://www.geeksforgeeks.org/decimal-add-method-in-c-sharp/)

此方法用于添加两个指定的十进制值。

> **语法:**公共静态小数 Add(小数 a1，小数 a2)；
> 
> **参数:**
> **a1** :该参数指定要添加的第一个值。
> **a2** :此参数指定第二个要添加的值。
> 
> **返回值**:T2 a1&*a2*的十进制和。

**例外情况:**如果 a1 和 a2 的和小于*小数的最小可能值*或*大于小数的最大可能值*，该方法将给出*overoveroverowexception*。

下面的程序说明了**小数的使用。加法(十进制，十进制)法**

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.Add(Decimal, Decimal) 
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal
            // variables
            Decimal a1 = .01m;
            Decimal a2 = .03m;

            // adding the two Decimal value
            // using Add() method;
            Decimal value = Decimal.Add(a1, a2);

            // Display the sum
            Console.WriteLine("Decimal Sum : {0}",
                                           value);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Decimal Sum : 0.04

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.Add(Decimal, Decimal)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 1.01m;
            Decimal a2 = Decimal.MaxValue;

            // adding the two Decimal value
            // using Add() method;
            Decimal value = Decimal.Add(a1, a2);

            // Display the sum
            Console.WriteLine("Decimal Sum : {0}",
                                           value);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.OverflowException

```