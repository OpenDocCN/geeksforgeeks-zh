# 小数。C# 中的求反()方法

> 原文:[https://www . geesforgeks . org/decimal-c-sharp 中的求反方法/](https://www.geeksforgeeks.org/decimal-negate-method-in-c-sharp/)

此方法用于获取指定的十进制值乘以负一的结果。

> **语法:**公共静态十进制否定(十进制 a)；
> 
> **参数:**
> **a** :该参数指定将要转换的小数。
> 
> **返回值:**一个十进制数，数值为*一*，但符号相反。但是零，如果*一*是零。

下面的程序说明了**小数的使用。求反(十进制)法**:

**例 1:** 当 a 为正时

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = 127.97m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the negative value
        Console.WriteLine("The negative value "+
                             "is : {0}", value);
    }
}
```

**Output:**

```cs
The negative value is : -127.97

```

**例 2:** 当 a 为负时

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = -12.39m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the value after
        // using negate method
        Console.WriteLine("The value is : {0}",
                                        value);
    }
}
```

**Output:**

```cs
The value is : 12.39

```

**例 3:** 如果 a 为零。

```cs
// C# program to demonstrate the
// Decimal.Negate(Decimal) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring the decimal variable
        Decimal a = 0.00m;

        // using Negate() method;
        Decimal value = Decimal.Negate(a);

        // Display the Negate value
        Console.WriteLine("The Negate value "+
                           "is : {0}", value);
    }
}
```

**Output:**

```cs
The Negate value is : 0.00

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . decimal . negative？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.negate?view=netframework-4.7.2)