# 小数。C# 中的 Round()方法| Set–1

> 原文:[https://www . geesforgeks . org/decimal-round-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/decimal-round-method-in-c-sharp-set-1/)

**小数。舍入方法**用于将一个值舍入到最接近的整数或指定的小数位数。该方法的重载列表中有以下 4 种方法:

*   `Round(Decimal)` 方法
*   `Round(Decimal, Int32)` 方法
*   `Round(Decimal, MidpointRounding)` 方法
*   `Round(Decimal, Int32, MidpointRounding)` 方法

在这里，我们将讨论前两种方法。

## `Decimal.Round(Decimal)` 方法

此方法用于将十进制值舍入到最接近的整数。

> **语法:** `public static Decimal Round(Decimal d);`
> 在这里，需要一个十进制数来取整。
>
> **返回值:** 该方法返回最接近 `d` 参数的整数。如果 `d` 在两个整数中间，其中一个是偶数，另一个是奇数，则返回偶数。
>
> **异常:** 如果结果超出十进制值的范围，此方法将引发 `OverflowException`。

下面的程序说明了 `Decimal.Round(Decimal)` 方法的使用:

### 例 1:

```cs
// C# program to demonstrate the
// Decimal.Round(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            decimal value = 184467440737095.51615M;

            // getting rounded decimal
            // using Round() method
            decimal round = Decimal.Round(value);

            // Display the value
            Console.WriteLine("Rounded value is {0}", round);
        }

        catch (OverflowException e)
        {
            Console.WriteLine("Value must not be out of bound");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Rounded value is 184467440737096
```

### 例 2: 适用于 `OverflowException`

```cs
// C# program to demonstrate the
// Decimal.Round(Decimal) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try
        {

            // Declaring and initializing value
            decimal value = 79228162514264337593543950335.5M;

            // getting rounded decimal
            // using Round() method
            decimal round = Decimal.Round(value);

            // Display the value
            Console.WriteLine("Rounded value is {0}", round);
        }

        catch (OverflowException e)
        {
            Console.WriteLine("Value must not be out of bound");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**编译时错误:**

> prog.cs(15, 51): error CS0594: 浮点常数超出了“decimal”类型的范围

## `Round(Decimal, Int32)` 方法

此方法用于将十进制值舍入到指定的小数位数。

> **语法:** `public static Decimal Round(Decimal d, Int32 decimals);`
>
> **参数:**
> **`d`:** 是要四舍五入的小数。
> **`decimals`:** 它是一个从 0 到 28 的值，指定要舍入到的小数位数。
>
> **返回值:** 该方法返回相当于 `d` 的小数，四舍五入到小数位数。
>
> **异常:** 如果 `decimals` 不是 0 到 28 的值，这个方法抛出 `ArgumentOutOfRangeException`。

下面的程序说明了 `Decimal.Round(Decimal, Int32)` 方法的使用:

### 例 1:

```cs
// C# program to demonstrate the
// Decimal.Round(Decimal, Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            decimal value = 7922816251426433759354.39503305M;

            // getting rounded decimal
            // using Round() method
            decimal round = Decimal.Round(value, 4);

            // Display the value
            Console.WriteLine("Rounded value is {0}", round);
        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("decimal place is not within bound");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Rounded value is 7922816251426433759354.3950
```

### 例 2: 为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// Decimal.Round(Decimal, Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try
        {

            // Declaring and initializing value
            decimal value = 7922816251426433759354.39503305M;

            // getting rounded decimal
            // using Round() method
            decimal round = Decimal.Round(value, 29);

            // Display the value
            Console.WriteLine("Rounded value is {0}", round);
        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("Decimal place is not within bound");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Decimal place is not within bound
Exception Thrown: System.ArgumentOutOfRangeException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.round?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.round?view=netframework-4.7.2)