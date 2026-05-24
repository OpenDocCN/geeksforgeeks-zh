# 小数。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/decimal-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/decimal-gethashcode-method-in-c-sharp-with-examples/)

**小数。GetHashCode** 方法用于获取当前 Decimal 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Decimal.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking decimal variables
        // having fractional part
        Decimal dec1 = 214748.78549M;

        // Getting the hash code for Decimal
        // using GetHashCode() method
        int result = dec1.GetHashCode();

        // Display the time
        Console.WriteLine("HashCode for Decimal is: {0}",
                                                 result);
    }
}
```

**Output:**

```cs
HashCode for Decimal is: 161795526

```

**例 2:**

```cs
// C# program to illustrate the
// Decimal.GetHashCode() Method
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

        // using GetHashCode() method
        int code = val.GetHashCode();

        // Display the hashcode
        Console.WriteLine("HashCode for {0} is {1}",
                                         val, code);
    }
}
```

**Output:**

```cs
HashCode for -79228162514264337593543950335 is -974127104
HashCode for 79228162514264337593543950335 is 1173356544

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . gethashcode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.gethashcode?view=netframework-4.7.2)