# 单身。C# 中的 GetHashCode()方法及示例

> 原文:[https://www . geesforgeks . org/single-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-gethashcode-method-in-c-sharp-with-examples/)

**单身。方法用于返回此实例的哈希代码。**

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了 **Single 的使用。GetHashCode()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Single.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value1
        float value1 = 10f;

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
HashCode is 1092616192

```

**例 2:**

```cs
// C# program to demonstrate the
// Single.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5f);
        get(9.5f);
        get(10000f);
        get(2327.5232f);
    }

    // defining get() method
    public static void get(float value1)
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
HashCode is 1084227584
HashCode is 1092091904
HashCode is 1176256512
HashCode is 1158772831

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . gethashcode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.gethashcode?view=netstandard-2.1)