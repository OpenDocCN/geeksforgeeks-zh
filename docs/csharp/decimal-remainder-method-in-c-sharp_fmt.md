# Decimal.Remainder 方法（C#）

> 原文：[https://www.geeksforgeeks.org/decimal-remainder-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-remainder-method-in-c-sharp/)

当在两个指定的十进制值之间进行除法运算时，此方法用于计算余数。

## 语法：
`public static decimal Remainder(decimal a1, decimal a2);`

## 参数：
*   `a1`：该参数指定被除数。
*   `a2`：此参数指定除数。

## 返回值：
返回 `a1` 除以 `a2` 后的余数。

## 异常：
*   `DivideByZeroException`：当 `a2` 为零时，会出现这种情况。
*   `OverflowException`：如果返回值小于 `MinValue` 或大于 `MaxValue`。

下面的程序说明了 `Decimal.Remainder(Decimal, Decimal)` 方法的使用：

## 例 1：
```cs
// C# program to demonstrate the
// Decimal.Remainder(Decimal, 
// Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = 1.11m;

            // dividing and getting the remainder
            // of the two Decimal value
            // using Remainder() method;
            Decimal value = Decimal.Remainder(a1, a2);

            // Display the remainder
            Console.WriteLine("Remainder is : {0}", value);
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
Remainder is : 0.69
```

## 例 2：适用于 `OverflowException`
```cs
// C# program to demonstrate the
// Decimal.Remainder(Decimal, 
// Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = Decimal.MaxValue;
            Decimal a2 = 0.02m;

            // dividing and getting the remainder
            // of the two Decimal value
            // using Remainder() method;
            Decimal value = Decimal.Remainder(a1, a2);

            // Display the remainder
            Console.WriteLine("Remainder is : {0}", value);
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

## 例 3：`DivideByZeroException` 程序
```cs
// C# program to demonstrate the
// Decimal.Remainder(Decimal,
// Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = 0.00m;

            // dividing and getting the remainder
            // of the two Decimal value
            // using Remainder() method;
            Decimal value = Decimal.Remainder(a1, a2);

            // Display the remainder
            Console.WriteLine("Remainder is : {0}", value);
        }

        catch (DivideByZeroException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**
```cs
Exception Thrown: System.DivideByZeroException
```

## 参考：
*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.remainder?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.remainder?view=netframework-4.7.2)