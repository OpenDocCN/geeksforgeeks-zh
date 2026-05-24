# 小数。C# 中的 GetTypeCode 方法及示例

> 原文:[https://www . geesforgeks . org/decimal-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/decimal-gettypecode-method-in-c-sharp-with-examples/)

**小数。GetTypeCode** 方法用于获取值类型 Decimal 的类型代码。

> **语法:**公共类型代码 gettype code()；
> 
> **返回值:**该方法返回枚举常量 Decimal。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Decimal.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking decimal variable
        // having fractional part
        Decimal dec1 = 214748.78549M;

        // Getting the typecode for Decimal
        // using GetTypeCode() method
        TypeCode result = dec1.GetTypeCode();

        // Display the time
        Console.WriteLine("TypeCode for Decimal is: {0}",
                                                 result);
    }
}
```

**Output:**

```cs
TypeCode for Decimal is: Decimal

```

**例 2:**

```cs
// C# program to illustrate the
// Decimal.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Decimal.MinValue);
        result(Decimal.MaxValue);
    }

    // result() method
    public static void result(decimal val)
    {

        // using GetTypeCode() method
        TypeCode code = val.GetTypeCode();

        // Display the hashcode
        Console.WriteLine("TypeCode for {0} is {1}",
                                         val, code);
    }
}
```

**Output:**

```cs
TypeCode for -79228162514264337593543950335 is Decimal
TypeCode for 79228162514264337593543950335 is Decimal

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . gettypecode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.gettypecode?view=netframework-4.7.2)