# C# | Int32。ToString 方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-int 32-tostring-method-set-1/](https://www.geeksforgeeks.org/c-sharp-int32-tostring-method-set-1/)

**Int32。ToString 方法**用于将当前 Int32 实例的数值转换为其等价的字符串表示形式。这个方法的重载列表中有 4 个方法如下:
这里，我们将讨论前两个方法。

#### ToString(表单提供商)方法

此方法用于使用指定的区域性特定格式信息将当前实例的数值转换为其等效的字符串表示形式。

**语法:**

```cs
public string ToString (IFormatProvider provider);
```

**参数:**该方法获取类型为*的对象，该对象提供特定于区域性的格式信息。
**返回值:**该方法以提供者参数指定的格式返回当前实例值的字符串表示形式。
**示例:***

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Int32.ToString(IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing Int32 value
        int s1 = 15;

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
The Value is 15 and provider is en-US
```