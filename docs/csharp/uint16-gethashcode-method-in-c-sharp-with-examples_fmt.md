# UInt16.GetHashCode 方法及示例

> 原文：[https://www.geeksforgeeks.org/uint16-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-gethashcode-method-in-c-sharp-with-examples/)

`UInt16.GetHashCode` 方法用于获取当前 `UInt16` 实例的哈希码。

## 语法

```cs
public override int GetHashCode();
```

## 返回值

这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用：

## 示例 1

```cs
// C# program to illustrate the
// UInt16.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Taking UInt16 variable
        // i.e. ushort data type
        ushort s1 = 124;

        // Getting the hash code for UInt16
        // using GetHashCode() method
        int result = s1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for UInt16 is: {0}",
                                        result);
    }
}
```

**输出：**

```cs
HashCode for UInt16 is: 124
```

## 示例 2

```cs
// C# program to illustrate the
// UInt16.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(UInt16.MinValue);
        result(UInt16.MaxValue);
    }

    // result() method
    public static void result(ushort val)
    {
        // using GetHashCode() method
        int code = val.GetHashCode();

        // Display the hashcode
        Console.WriteLine("HashCode for {0} is {1}",
                                  val, code);
    }
}
```

**输出：**

```cs
HashCode for 0 is 0
HashCode for 65535 is 65535
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint16.gethashcode?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.gethashcode?view=netstandard-2.1)