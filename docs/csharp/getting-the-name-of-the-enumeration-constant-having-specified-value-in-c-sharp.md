# 获取 C# 中具有指定值的枚举常量的名称

> 原文:[https://www . geesforgeks . org/get-name-of-enumeration-constant-having-specified-value-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-name-of-the-enumeration-constant-having-specified-value-in-c-sharp/)

**枚举。GetName(Type，Object)方法**用于获取指定枚举中具有指定值的常量的名称。

**语法:**

```cs
public static string GetName (Type enumType, object value);
```

**参数:**

*   **Enumeration type:** is an enumeration type.
*   **Value:** It is the value of a specific enumeration constant in terms of its basic type.

**返回:**是一个字符串，包含枚举类型中枚举常量的名称，如果找不到这样的常量，其值为值或空。

**异常:**

*   **参数空异常:**如果*枚举类型*或值为空。
*   **参数异常:**如果*枚举类型*不是*枚举*或*值*既不是枚举类型，也没有与*枚举类型*相同的基础类型。

**例:**

```cs
// C# program to illustrate the
// Enum.GetName(Type, Object) Method
using System;

enum Animals { Dog,
               Cat,
               Cow,
               Monkey };

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // using the method
        Console.WriteLine("2nd value is {0}", Enum.GetName(typeof(Animals), 1));
        Console.WriteLine("4th value is {0}", Enum.GetName(typeof(Animals), 3));
    }
}
```

**输出:**

```cs
2nd value is Cat
4th value is Monkey

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。枚举。getname？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.getname?view=netframework-4.8)