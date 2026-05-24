# 如何在 C# 中获取枚举的 typecode？

> 原文:[https://www . geeksforgeeks . org/如何获取 c-sharp 中枚举的类型代码/](https://www.geeksforgeeks.org/how-to-get-the-typecode-for-enum-in-c-sharp/)

**枚举。GetTypeCode 方法**用于获取该枚举成员的底层类型的类型代码。

**语法:**

```cs
public TypeCode GetTypeCode ();
```

**返回:**这个方法返回这个实例的基础类型的类型代码。

**异常:**如果枚举类型未知，此方法将给出*无效操作异常*。

**例:**

```cs
// C# program to illustrate the
// Enum.GetTypeCode() Method
using System;

class GFG {

    enum Color {Blue, Black };

    // Main Method
    public static void Main(String[] args)
    {
        Color c1 = Color.Blue;
        Console.Write("TypeCode of Enum Constant " + c1 + " : ");

        // Using the GetTypeCode() Method
        Console.WriteLine(c1.GetTypeCode());

        Color c2 = Color.Black;
        Console.Write("TypeCode of Enum Constant " + c2 + " : ");

        // Using the GetTypeCode Method
        Console.WriteLine(c2.GetTypeCode());
    }
}
```

**输出:**

```cs
TypeCode of Enum Constant Blue : Int32
TypeCode of Enum Constant Black : Int32

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。枚举。gettypecode？view = net framework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.gettypecode?view=netframework-4.8)sfdsfsdf