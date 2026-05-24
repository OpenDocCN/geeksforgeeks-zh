# UInt64.ToString 方法在 C# 中的使用（含示例）| Set–2

> 原文：[https://www.geeksforgeeks.org/uint64-tostring-method-in-c-sharp-with-examples-set-2/](https://www.geeksforgeeks.org/uint64-tostring-method-in-c-sharp-with-examples-set-2/)

**`UInt64.ToString` 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法：
*   `ToString(IFormatProvider)` 方法
*   `ToString(String, IFormatProvider)` 方法
*   `ToString()` 方法
*   `ToString(String)` 方法

在这里，我们将讨论最后两种方法。

## ToString() 方法

此方法用于将当前实例的数值转换为其等效的字符串表示形式。

**语法：**

```cs
public override string ToString ();
```

**返回值：** 此方法返回当前实例值的字符串表示形式，由 0 到 9 的数字序列组成，不带符号或前导零。

**示例：**

```cs
// C# program to illustrate the
// UInt64.ToString() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        Console.WriteLine("The String values are: ");

        // calling the method
        result(UInt64.MaxValue);
        result(UInt64.MinValue);
        result(4946515);
        result(8786786456);
    }

    // result() method
    public static void result(ulong p)
    {
        // using ToString() method
        string str = p.ToString();

        // Display the value
        Console.WriteLine("The Corresponding String "
                         + "Value is: {0}", str);
    }
}
```

**输出：**

```cs
The String values are: 
The Corresponding String Value is: 18446744073709551615
The Corresponding String Value is: 0
The Corresponding String Value is: 4946515
The Corresponding String Value is: 8786786456
```

## ToString(String) 方法

此方法用于使用指定的格式将当前实例的数值转换为其等效的字符串表示形式。

**语法：**

```cs
public string ToString (string format);
```

**参数：** 此方法采用标准或自定义数字格式字符串。

**返回值：** 该方法返回由 `format` 指定的当前实例值的字符串表示形式。

**异常：** 如果 `format` 参数无效，此方法将给出 `FormatException`。

**示例：**

```cs
// C# program to demonstrate the
// UInt64.ToString(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // Declaring and initializing value
            ulong val = 13244214;

            // Declaring and initializing format
            string format = "E2";

            // using the method
            string result = val.ToString(format);

            // Display the result
            Console.WriteLine("The value of string is {0}", result);
        }
        catch (FormatException e) {
            Console.WriteLine("Format is invalid.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
The value of string is 1.32E+007
```

**参考：**
*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint64.tostring?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.tostring?view=netstandard-2.1)