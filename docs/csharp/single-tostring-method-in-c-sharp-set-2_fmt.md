## Single.ToString() 方法在 C# 中的应用 | 集合 – 2

> 原文：[https://www.geeksforgeeks.org/single-tostring-method-in-c-sharp-set-2/](https://www.geeksforgeeks.org/single-tostring-method-in-c-sharp-set-2/)

`Single.ToString()` 方法用于将当前实例的数值转换为其等价的字符串表示形式。该方法的重载列表中有以下 4 种方法：

*   `ToString()`
*   `ToString()`
*   `ToString(IFormatProvider)`
*   `ToString(String, IFormatProvider)`

在这里，我们将讨论最后两种方法。

### `ToString(IFormatProvider)` 方法

此方法用于使用指定的区域性特定格式信息将当前实例的数值转换为其等效的字符串表示形式。

**语法：**

```cs
public string ToString (IFormatProvider provider);
```

**参数：** 该方法获取一个类型为 `IFormatProvider` 的对象，该对象提供特定于区域性的格式信息。

**返回值：** 此方法以 `provider` 参数指定的格式返回当前实例值的字符串表示形式。

**示例：**

```cs
// C# program to demonstrate
// Single.ToString(IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing
        // Single value
        float s1 = 65465.67867f;

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

**输出：**

```cs
The Value is 65465.68 and provider is en-US
```

### `Single.ToString(String, IFormatProvider)` 方法

此方法用于使用指定的格式和区域性特定的格式信息将此实例的数值转换为其等效的字符串表示形式。

**语法：**

```cs
public string ToString (string format, IFormatProvider provider);
```

**参数：**

> **`format`：** 标准或自定义数字格式字符串。
> **`provider`：** 它是一个提供特定于区域性的格式信息的对象。

**返回值：** 该方法返回由 `format` 和 `provider` 参数指定的当前实例的字符串表示形式。

**示例：**

```cs
// C# program to demonstrate the
// Single.ToString(String, IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing Single value
        float s1 = Single.MaxValue;

        // creating and initializing
        // the object of CultureInfo
        CultureInfo provider = new CultureInfo("es-ES");

        // declaring and initializing format
        string format = "N";

        // using the method
        string str = s1.ToString(format, provider);

        // Displaying the details
        Console.WriteLine("The value is {0}", str);
        Console.WriteLine("The Format is {0}", format);
        Console.WriteLine("The Provider is {0}", provider.Name);
    }
}
```

**输出：**

```cs
The value is 340.282.300.000.000.000.000.000.000.000.000.000.000,00
The Format is N
The Provider is es-ES
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.tostring?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.tostring?view=netstandard-2.1)