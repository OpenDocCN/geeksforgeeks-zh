# Int16.GetTypeCode 方法及 C# 示例

> 原文: [https://www.geeksforgeeks.org/int16-gettypecode-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-gettypecode-method-in-c-sharp-with-examples/)

`Int16.GetTypeCode` 方法用于获取值类型 `Int16` 的类型代码。

> **语法:**
> `public TypeCode GetTypeCode();`
>
> **返回值:**
> 该方法返回枚举常量 `Int16`。

以下程序说明了上述方法的使用:

## 例 1

```cs
// C# program to illustrate the
// Int16.GetTypeCode() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Taking short value
        // i.e. Int16
        short s1 = 123;

        // Getting the typecode for Int16
        // using GetTypeCode() method
        TypeCode result = s1.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for Int16 is: {0}", result);
    }
}
```

**输出:**

```cs
TypeCode for Int16 is: Int16
```

## 例 2

```cs
// C# program to illustrate the
// Int16.GetTypeCode() Method
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
        // using GetTypeCode() method
        TypeCode code = val.GetTypeCode();

        // Display the TypeCode
        Console.WriteLine("TypeCode for {0} is {1}", val, code);
    }
}
```

**输出:**

```cs
TypeCode for -32768 is Int16
TypeCode for 32767 is Int16
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.int16.gettypecode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.gettypecode?view=netframework-4.7.2)