# UInt64。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/uint 64-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-gethashcode-method-in-c-sharp-with-examples/)

**UInt64。GetHashCode** 方法用于获取当前 UInt64 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// UInt64.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking UInt64 variable
        // i.e. ulong data type
        ulong s1 = 1654651654;

        // Getting the hash code 
        // using GetHashCode() method
        int result = s1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for UInt64 is: {0}",
                                                result);
    }
}
```

**Output:**

```cs
HashCode for UInt64 is: 1654651654

```

**例 2:**

```cs
// C# program to illustrate the
// UInt64.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt64.MinValue);
        result(UInt64.MaxValue);
    }

    // result() method
    public static void result(ulong val)
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
HashCode for 0 is 0
HashCode for 18446744073709551615 is 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 64 . gethashcode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.gethashcode?view=netstandard-2.1)