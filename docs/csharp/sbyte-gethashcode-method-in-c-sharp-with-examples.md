# SByte。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/sbyte-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sbyte-gethashcode-method-in-c-sharp-with-examples/)

**SByte。GetHashCode** 方法用于获取当前 *SByte* 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// SByte.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking SByte variable
        sbyte val = 23;

        // Getting the hash code for SByte
        // using GetHashCode() method
        int result = val.GetHashCode();

        // Display the hashcode
        Console.WriteLine("HashCode for SByte is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
HashCode for SByte is: 5911

```

**例 2:**

```cs
// C# program to illustrate the
// SByte.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(SByte.MinValue);
        result(SByte.MaxValue);
    }

    // result() method
    public static void result(sbyte val)
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
HashCode for -128 is 32640
HashCode for 127 is 32639

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . gethashcode？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.gethashcode?view=netcore-2.1)