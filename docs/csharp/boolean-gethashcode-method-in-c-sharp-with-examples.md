# 布尔。C# 中的 GetHashCode()方法及示例

> 原文:[https://www . geesforgeks . org/boolean-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/boolean-gethashcode-method-in-c-sharp-with-examples/)

**布尔。方法用于返回此实例的哈希代码。**

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

下面的程序说明了**布尔值的使用。GetHashCode()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Boolean.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value1
        bool value1 = true;

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
HashCode is 1

```

**例 2:**

```cs
// C# program to demonstrate the
// Boolean.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(true);
        get(false);
    }

    // defining get() method
    public static void get(bool value1)
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
HashCode is 1
HashCode is 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . boolean . gethashcode？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.gethashcode?view=netframework-4.8)