# 获取 C# 中具有指定值的枚举常量的名称

> 原文：[https://www.geeksforgeeks.org/getting-the-name-of-the-enumeration-constant-having-specified-value-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-name-of-the-enumeration-constant-having-specified-value-in-c-sharp/)

`Enum.GetName(Type, Object)` 方法用于获取指定枚举中具有指定值的常量的名称。

## 语法

```csharp
public static string GetName (Type enumType, object value);
```

## 参数

*   `enumType`：枚举类型。
*   `value`：特定枚举常量的值（以其基本类型表示）。

## 返回

一个字符串，包含枚举类型中具有指定值的枚举常量的名称；如果找不到这样的常量，则为 `null`。

## 异常

*   `ArgumentNullException`：如果 `enumType` 或 `value` 为 `null`。
*   `ArgumentException`：如果 `enumType` 不是 `Enum`，或 `value` 既不是 `enumType` 类型，也没有与 `enumType` 相同的基础类型。

## 示例

```csharp
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

## 输出

```cs
2nd value is Cat
4th value is Monkey
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.enum.getname?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.getname?view=netframework-4.8)