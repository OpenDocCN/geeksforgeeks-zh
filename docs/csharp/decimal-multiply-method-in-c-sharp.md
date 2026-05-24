# 小数。C# 中的乘法()方法

> 原文:[https://www . geeksforgeeks . org/decimal-乘法-in-c-sharp/](https://www.geeksforgeeks.org/decimal-multiply-method-in-c-sharp/)

此方法用于乘以两个指定的十进制值。

> **语法:**公共静态十进制乘法(十进制 a1，十进制 a2)；
> **参数:**
> **a1** :该参数指定被乘数。
> **a2** :此参数指定乘数。
> **返回值:***a1*&*a2*相乘的结果。

**异常:**如果返回值小于最小值或大于最大值，该方法将给出*overoverowexception*。

下面的程序说明了**小数的使用。乘法(十进制，十进制)**方法

**例 1:**

## C#

```cs
// C# program to demonstrate the
// Decimal.Multiply(Decimal,
// Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = 2.01m;

            // multiplying the two Decimal value
            // using Multiplying() method;
            Decimal value = Decimal.Multiply(a1, a2);

            // Display the product
            Console.WriteLine("Result of multiplication : {0}",
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
Result of multiplication : 8.0802
```

**示例 2:*飞越异常*的**程序

## C#

```cs
// C# program to demonstrate the
// Decimal.Multiply(Decimal,
// Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = Decimal.MaxValue;

            // multiplying the two Decimal value
            // using Multiply() method;
            Decimal value = Decimal.Multiply(a1, a2);

            // Display the product
            Console.WriteLine("Result of multiplication : {0}",
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