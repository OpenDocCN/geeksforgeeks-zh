# UInt32。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/uint 32-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-gethashcode-method-in-c-sharp-with-examples/)

**UInt32。GetHashCode** 方法用于获取当前 UInt32 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// UInt32.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking UInt32 variable
        // i.e. uint data type
        uint s1 = 13224;

        // Getting the hash code 
        // using GetHashCode() method
        int result = s1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for UInt32 is: {0}",
                                                result);
    }
}
```

**Output:**

```cs
HashCode for UInt32 is: 13224

```

**例 2:**

```cs
// C# program to illustrate the
// UInt32.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt32.MinValue);
        result(UInt32.MaxValue);
    }

    // result() method
    public static void result(uint val)
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
HashCode for 4294967295 is -1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . gethashcode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.gethashcode?view=netstandard-2.1)