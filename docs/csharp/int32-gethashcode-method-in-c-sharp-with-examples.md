# Int32。C# 中的 GetHashCode 方法及示例

> 原文:[https://www . geesforgeks . org/int 32-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-gethashcode-method-in-c-sharp-with-examples/)

**Int32。GetHashCode** 方法用于获取当前 Int32 实例的 HashCode。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the
// Int32.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Taking Int32 variable
        int val = 32523;

        // Getting the hash code for Int32
        // using GetHashCode() method
        int result = val.GetHashCode();

        // Display the hashcode
        Console.WriteLine("HashCode for Int32 is: {0}",
                                               result);
    }
}
```

**Output:**

```cs
HashCode for Int32 is: 32523

```

**例 2:**

```cs
// C# program to illustrate the
// Int32.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Int32.MinValue);
        result(Int32.MaxValue);
    }

    // result() method
    public static void result(int val)
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
HashCode for -2147483648 is -2147483648
HashCode for 2147483647 is 2147483647

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . gethashcode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.gethashcode?view=netframework-4.7.2)