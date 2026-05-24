# C# `Type.GetHashCode()` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-type-gethashcode-method/](https://www.geeksforgeeks.org/c-sharp-type-gethashcode-method/)

`Type.GetHashCode()` 方法用于返回这个实例的哈希代码。

> **语法：** `public override int GetHashCode()；`
>
> **返回值：** 该方法返回当前实例的哈希代码。

以下程序说明了 `Type.GetHashCode()` 方法的使用：

## 例 1：

```cs
// C# program to demonstrate the
// Type.GetHashCode() Method
using System;
using System.Globalization;
using System.Reflection;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(Dictionary<, >);

        // Getting hashcode of given type
        // using GetHashCode() Method
        int hash = objType.GetHashCode();

        // Display the Result
        Console.Write("Hashcode is {0}", hash);
    }
}
```

**Output:**

```cs
Hashcode is 32340152
```

## 例 2：

```cs
// C# program to demonstrate the
// Type.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(typeof(int));
        get(typeof(string));
        get(typeof(decimal));
        get(typeof(float));
    }

    // defining get() method
    public static void get(Type objType)
    {
        // Getting hashcode of given type
        // using GetHashCode() Method
        int hash = objType.GetHashCode();

        // Display the Result
        Console.WriteLine("Hashcode of {0} is {1}", objType, hash);
    }
}
```

**Output:**

```cs
Hashcode of System.Int32 is 18784216
Hashcode of System.String is 18793840
Hashcode of System.Decimal is 19137544
Hashcode of System.Single is 18792864
```

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.gethashcode?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.gethashcode?view=netframework-4.8)