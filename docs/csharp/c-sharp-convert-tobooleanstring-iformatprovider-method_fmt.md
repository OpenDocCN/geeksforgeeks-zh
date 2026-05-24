# C# Convert.ToBoolean(String, IFormatProvider) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-tobooleanstring-iformatprovider-method/](https://www.geeksforgeeks.org/c-sharp-convert-tobooleanstring-iformatprovider-method/)

此方法用于使用指定的区域性特定格式信息，将逻辑值的指定字符串表示形式转换为其布尔等效形式。

## 语法

```cs
public static bool ToBoolean (string value, IFormatProvider provider);
```

## 参数

*   `value`：是包含 `TrueString` 或 `FalseString` 值的字符串。
*   `provider`：它是一个提供区域性特定格式信息的对象。此参数被忽略。

## 返回值

如果 `value` 等于 `TrueString`，则该方法返回 `true`，如果 `value` 等于 `FalseString` 或 `null`，则返回 `false`。

## 异常

如果 `value` 不等于 `TrueString` 或 `FalseString`，此方法将抛出 `FormatException`。

以下程序说明了 `Convert.ToBoolean(String, IFormatProvider)` 方法的使用。

## 示例 1

```cs
// C# program to demonstrate the
// Convert.ToBoolean() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = new CultureInfo("en-US");

            // declaring and initializing String array
            String[] values = { null, "true",
                        "False", " false " };

            // calling get() Method
            Console.WriteLine("Converted bool value "+
                            "of specified strings: ");

            for (int j = 0; j < values.Length; j++) {
                get(values[j], cultures);
            }
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string s, CultureInfo cultures)
    {

        // converting string to specified bool
        bool val = Convert.ToBoolean(s, cultures);

        // display the converted string
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**

```cs
Converted bool value of specified strings: 
 False,  True,  False,  False,
```

## 示例 2：为 `FormatException`

```cs
// C# program to demonstrate the
// Convert.ToBoolean() Method
using System;
using System.Globalization;
class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of CultureInfo
            CultureInfo cultures = new CultureInfo("en-US");

            // declaring and initializing String array
            String[] values = { null, "true",
                    "False", " false ", "" };

            // calling get() Method
            Console.WriteLine("Converted bool value"+
                          " of specified strings: ");

            for (int j = 0; j < values.Length; j++) {
                get(values[j], cultures);
            }
        }

        catch (FormatException e) {
            Console.WriteLine("\n");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(string s, CultureInfo cultures)
    {

        // converting string to specified bool
        bool val = Convert.ToBoolean(s, cultures);

        // display the converted string
        Console.Write(" {0}, ", val);
    }
}
```

**输出：**

```cs
Converted bool value of specified strings: 
 False,  True,  False,  False,

Exception Thrown: System.FormatException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.toboolean?view=netframework-4.7.2#System_Convert_ToBoolean_System_String_System_IFormatProvider_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.toboolean?view=netframework-4.7.2#System_Convert_ToBoolean_System_String_System_IFormatProvider_)