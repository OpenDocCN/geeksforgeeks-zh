# 布尔。C# 中的 ToString(表单提供者)方法

> 原文:[https://www . geeksforgeeks . org/boo clion-tostringiformatprovider-method-in-c-sharp/](https://www.geeksforgeeks.org/booolean-tostringiformatprovider-method-in-c-sharp/)

**布尔。ToString(IFormatProvider)方法**用于将当前实例的值转换为其等效的字符串表示形式，该字符串表示形式为“*真*或“*假*

**语法:**

```cs
public string ToString (IFormatProvider provider);
```

**参数:**该方法取一个预留的*表单提供者*类型的对象。

**返回值:**如果该实例的值为*真*，则该方法返回*真字符串*，如果该实例的值为*假*，则返回*假字符串*。

**示例:**

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

**Output:**

```cs
The Value is True and provider is en-US

```

**注意:***提供程序*参数被保留，因为它在此方法的执行中不会有任何贡献。这意味着，与大多数具有提供程序参数的方法不同，此方法不反映区域性特定的设置。

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。布尔型。tostring？view = net framework-4.8 # System _ Boolean _ ToString _ System _ IFormatProvider _](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.tostring?view=netframework-4.8# System_Boolean_ToString_System_IFormatProvider_)