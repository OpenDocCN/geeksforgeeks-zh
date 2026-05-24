# 小数。C# 中的 ToOACurrency()方法

> 原文:[https://www . geeksforgeeks . org/decimal-tooaccurrency-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-tooacurrency-method-in-c-sharp/)

**小数。tooaccurrency(Decimal)方法**用于将指定的 Decimal 值转换为等效的 OLE 自动化货币值，该值包含在 64 位有符号整数中。

> **语法:**公共静态长 ToOACurrency(十进制值)；
> 这里，需要十进制数进行转换。
> 
> **返回值:**该方法返回一个 64 位有符号整数，其中包含值的 OLE 自动化等价物。

下面的程序说明了*小数的使用。*方法

**例 1:**

```cs
// C# program to demonstrate the
// Decimal.ToOACurrency() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Decimal curr = 40;

        // A 64-bit signed integer that contains
        // the OLE Automation equivalent of value.
        long value = Decimal.ToOACurrency(curr);

        // Display the HashCode
        Console.WriteLine("Equivalent long value is {0}", value);
    }
}
```

**Output:**

```cs
Equivalent long value is 400000

```

**例 2:**

```cs
// C# program to demonstrate the
// Decimal.ToOACurrency() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        Console.WriteLine("Equivalent long value are respectivily");
        get(20);
        get(30);
        get(40);
        get(4294967295);
    }

    // defining get() method
    public static void get(decimal curr)
    {

        // getting Equivalent decimal value
        // using ToOACurrency() method
        long value = Decimal.ToOACurrency(curr);

        // Display the HashCode
        Console.WriteLine("{0}", value);
    }
}
```

**Output:**

```cs
Equivalent long value are respectivily
200000
300000
400000
42949672950000

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . tooa currency？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tooacurrency?view=netframework-4.7.2)