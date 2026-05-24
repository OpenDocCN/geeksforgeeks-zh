# 布尔.ToString(IFormatProvider)方法

> 原文：[https://www.geeksforgeeks.org/boolean-tostringiformatprovider-method-in-c-sharp/](https://www.geeksforgeeks.org/boolean-tostringiformatprovider-method-in-c-sharp/)

`Boolean.ToString(IFormatProvider)`方法用于将当前实例的值转换为其等效的字符串表示形式，该字符串表示形式为“`true`”或“`false`”。

## 语法

```cs
public string ToString (IFormatProvider provider);
```

## 参数

该方法取一个预留的`IFormatProvider`类型的对象。

## 返回值

如果该实例的值为`true`，则该方法返回字符串“`True`”，如果该实例的值为`false`，则返回字符串“`False`”。

## 示例

```cs
// C# program to demonstrate
// Boolean.ToString(IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing
        // Boolean value
        bool s1 = true;

        // creating and initializing
        // the object of CultureInfo
        CultureInfo provider = new CultureInfo("en-us");

        // Using the method
        string str = s1.ToString(provider);

        // Display the value
        Console.WriteLine("The Value is {0} and provider is {1}",
                                 str, provider.Name);
    }
}
```

## 输出

```cs
The Value is True and provider is en-US
```

## 注意

`provider`参数被保留，因为它在此方法的执行中不会有任何贡献。这意味着，与大多数具有提供程序参数的方法不同，此方法不反映区域性特定的设置。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.boolean.tostring?view=netframework-4.8#System_Boolean_ToString_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.tostring?view=netframework-4.8#System_Boolean_ToString_System_IFormatProvider_)