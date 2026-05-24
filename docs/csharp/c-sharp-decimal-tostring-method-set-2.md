# C# |十进制。ToString 方法| Set -2

> 原文:[https://www . geesforgeks . org/c-sharp-decimal-tostring-method-set-2/](https://www.geeksforgeeks.org/c-sharp-decimal-tostring-method-set-2/)

**小数。ToString()方法**用于将当前实例的数值转换为其等价的字符串表示形式。该方法重载列表中有 4 种方法如下:

*   **串(弦)法**
*   **ToString()方法**
*   **ToString(表单提供者)方法**
*   **字符串(字符串，表单提供者)方法**

在这里，我们将讨论最后两种方法。

#### ToString(表单提供商)方法

此方法用于使用指定的区域性特定格式信息将当前实例的数值转换为其等效的字符串表示形式。
**语法:**

```cs
public string ToString (IFormatProvider provider);
```

**参数:**该方法获取类型为*的对象，该对象提供特定于区域性的格式信息。
**返回值:**该方法以提供者参数指定的格式返回当前对象值的字符串表示形式。
**例:*** 

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Decimal.ToString(IFormatProvider)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing
        // Decimal value
        decimal d1 = 568912m;

        // creating and initializing
        // the object of CultureInfo
        CultureInfo provider = new CultureInfo("en-us");

        // using the method
        string value = d1.ToString(provider);

        // Display the value
        Console.WriteLine("The Value is {0} and provider is {1}",
                                           value, provider.Name);
    }
}
```

**Output:** 

```cs
The Value is 568912 and provider is en-US
```