# Int64。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/int 64-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-gethashcode-method-in-c-sharp-with-examples/)

**Int64。GetHashCode** 方法用于获取当前 Int64 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Int64.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking Int64 variable
        // i.e. long data type
        long s1 = 458732523;

        // Getting the hash code for Int64
        // using GetHashCode() method
        int result = s1.GetHashCode();

        // Display the HashCode 
        Console.WriteLine("HashCode for Int64 is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
HashCode for Int64 is: 458732523

```

**例 2:**

```cs
// C# program to illustrate the
// Int64.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Int64.MinValue);
        result(Int64.MaxValue);
    }

    // result() method
    public static void result(long val)
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
HashCode for -9223372036854775808 is -2147483648
HashCode for 9223372036854775807 is -2147483648

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 64 . gethashcode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.gethashcode?view=netframework-4.7.2)