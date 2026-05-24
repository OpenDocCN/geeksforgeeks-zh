# 翻倍。C# 中的 IsFinite()方法

> 原文:[https://www . geesforgeks . org/double-is inite-method-in-c-sharp/](https://www.geeksforgeeks.org/double-isfinite-method-in-c-sharp/)

**翻倍。IsFinite()方法**用于检查双精度值是否越界。

> **语法:**公共静态 bool IsFinite(双精度值)；
> 
> **返回值:**如果值是有限的，该方法返回*真*，否则返回*假*。

下面的程序说明了 *Double 的使用。IsFinite()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Double.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = 10d;

        // using IsFinite() method
        bool value = Double.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**Output:**

```cs
10 is finite

```

**例 2:**

```cs
// C# program to demonstrate the
// Double.IsFinite() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        double value1 = Math.Pow(2, 1000000000000);

        // using IsFinite() method
        bool value = Double.IsFinite(value1);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is finite", value1);
        else
            Console.WriteLine("{0} is not finite", value1);
    }
}
```

**Output:**

```cs
Infinity is not finite

```