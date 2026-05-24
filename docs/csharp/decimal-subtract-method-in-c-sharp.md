# 小数。C# 中的减法()方法

> 原文:[https://www . geesforgeks . org/decimal-减法-in-c-sharp/](https://www.geeksforgeeks.org/decimal-subtract-method-in-c-sharp/)

此方法用于从一个指定的十进制值中减去另一个指定的十进制值。

> **语法:**公共静态十进制减法(十进制 a1，十进制 a2)；
> 
> **参数:**
> **a1** :该参数指定被减数。
> **a2** :此参数指定减数。
> 
> **返回值**:从 *a1* 中减去 *a2* 的结果。

**异常:**如果返回值小于*最小值*或大于*最大值*，该方法将给出*overoverover exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.Subtract(Decimal, Decimal)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal
            // variables
            Decimal a1 = .01m;
            Decimal a2 = .03m;

            // Subtracting the two Decimal value
            // using Subtract() method
            Decimal value = Decimal.Subtract(a1, a2);

            // Display the Result
            Console.WriteLine("Result is : {0}",
                                         value);
        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Result is : -0.02

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// Decimal.Subtract(Decimal, Decimal)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = Decimal.MinValue;
            Decimal a2 = Decimal.MaxValue;

            // Subtracting the two Decimal value
            // using Subtract() method;
            Decimal value = Decimal.Subtract(a1, a2);

            // Display the Result
            Console.WriteLine("Result is : {0}",
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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal .减法？视图=netcore-2.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.subtract?view=netcore-2.2)