# 翻倍。C# 中的 GetHashCode()方法

> 原文:[https://www . geesforgeks . org/double-gethashcode-method-in-c-sharp/](https://www.geeksforgeeks.org/double-gethashcode-method-in-c-sharp/)

**翻倍。方法用于返回此实例的哈希代码。**

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

下面的程序说明了 **Double 的使用。GetHashCode()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Double.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value1
        double value1 = 10d;

        // getting the HashCode
        // using GetHashCode() method
        int value = value1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode is {0}", value);
    }
}
```

**Output:**

```cs
HashCode is 1076101120

```

**例 2:**

```cs
// C# program to demonstrate the
// Double.Equals(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5d);
        get(5.5d);
        get(10d);
        get(7.5d);
    }

    // defining get() method
    public static void get(double value1)
    {

        // getting the HashCode
        // using GetHashCode() method
        int value = value1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode is {0}", value);
    }
}
```

**Output:**

```cs
HashCode is 1075052544
HashCode is 1075183616
HashCode is 1076101120
HashCode is 1075707904

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . double . gethashcode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.double.gethashcode?view=netframework-4.7.2)