# C# | Int64。ToString 方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-int 64-tostring-method-set-1/](https://www.geeksforgeeks.org/c-sharp-int64-tostring-method-set-1/)

**Int64。ToString 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法:

1.  **ToString(表单提供者)方法**
2.  **字符串(字符串，表单提供者)方法**
3.  **ToString()方法**
4.  **串(弦)法**

这里我们将讨论前两种方法。

#### ToString(表单提供商)方法

此方法用于使用指定的区域性特定格式信息将此实例的数值转换为其等效的字符串表示形式。
**语法:**

```cs
public string ToString (IFormatProvider provider);
```

**参数:**该方法获取类型为*的对象，该对象提供特定于区域性的格式信息。
**返回值:**该方法以*提供程序*参数指定的格式返回当前对象值的字符串表示形式。
**示例:***

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Int64.ToString(IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing
        // Int64 value
        long val = Int64.MaxValue;

        // creating and initializing
        // the object of CultureInfo
        CultureInfo provider = new CultureInfo("en-us");

        // using the method
        string str = val.ToString(provider);

        // Display the value
        Console.WriteLine("The Value is {0} and provider is {1}",
                                             str, provider.Name);
    }
}
```

**Output:** 

```cs
The Value is 9223372036854775807 and provider is en-US
```