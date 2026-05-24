# Int16.GetHashCode 方法及示例

> 原文：[https://www.geeksforgeeks.org/int16-gethashcode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-gethashcode-method-in-c-sharp-with-examples/)

`Int16.GetHashCode` 方法用于获取当前 `Int16` 实例的哈希码。

## 语法
```csharp
public override int GetHashCode();
```

## 返回值
此方法返回一个 32 位有符号整数哈希码。

以下程序说明了上述方法的使用：

## 示例 1
```csharp
// C# program to illustrate the
// Int16.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Taking Int16 variable
        // i.e. short data type
        short s1 = 124;

        // Getting the hash code for Int16
        // using GetHashCode() method
        int result = s1.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for Int16 is: {0}", result);
    }
}
```

**输出：**
```
HashCode for Int16 is: 8126588
```

## 示例 2
```csharp
// C# program to illustrate the
// Int16.GetHashCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // using result() Method
        result(Int16.MinValue);
        result(Int16.MaxValue);
    }

    // result() method
    public static void result(short val)
    {
        // using GetHashCode() method
        int code = val.GetHashCode();

        // Display the hashcode
        Console.WriteLine("HashCode for {0} is {1}", val, code);
    }
}
```

**输出：**
```
HashCode for -32768 is -2147450880
HashCode for 32767 is 2147450879
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.int16.gethashcode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.gethashcode?view=netframework-4.7.2)