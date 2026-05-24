# UInt32.Parse(string) 方法详解（C# 示例）

> 原文：[https://www.geeksforgeeks.org/uint32-parsestring-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-parsestring-method-in-c-sharp-with-examples/)

`UInt32.Parse(string)` 方法用于将数字的字符串表示转换为其等效的 32 位无符号整数。

## 语法

```cs
public static uint Parse (string str);
```

这里，`str` 是包含要转换的数字的字符串。`str` 的格式为 `【可选空格】【可选符号】数字【可选空格】`。这个符号可以是正的，也可以是负的。但是负号只能和零一起使用，否则会抛出 `OverflowException`。

## 返回值

返回一个 32 位无符号整数，相当于 `str` 中包含的数字。

## 异常

*   `ArgumentNullException`：如果 `str` 为 `null`。
*   `FormatException`：如果 `str` 格式不正确。
*   `OverflowException`：如果 `str` 代表小于 `UInt32.MinValue` 或大于 `UInt32.MaxValue` 的数字。

以下程序说明了上述方法的使用：

## 例 1

```cs
// C# program to demonstrate
// UInt32.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // passing different values
        // to the method to check
        checkParse("4294967295");
        checkParse("14244,784");
        checkParse("-457589");
        checkParse(" 784845");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {
        try {
            // declaring UInt32 variable
            uint val;

            // getting parsed value
            val = UInt32.Parse(input);
            Console.WriteLine("'{0}' parsed as {1}", input, val);
        }
        catch (OverflowException) {
            Console.WriteLine("Can't Parsed '{0}'", input);
        }
        catch (FormatException) {
            Console.WriteLine("Can't Parsed '{0}'", input);
        }
    }
}
```

**Output:**

```cs
'4294967295' parsed as 4294967295
Can't Parsed '14244, 784'
Can't Parsed '-457589'
' 784845' parsed as 784845
```

## 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// UInt32.Parse(String) Method
// for ArgumentNullException
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // passing null value as a input
            checkParse(null);
        }
        catch (ArgumentNullException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (FormatException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining checkparse method
    public static void checkParse(string input)
    {
        // declaring UInt32 variable
        uint val;

        // getting parsed value
        val = UInt32.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint32.parse?view=netframework-4.7.2#System_UInt32_Parse_System_String_](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.parse?view=netframework-4.7.2#System_UInt32_Parse_System_String_)