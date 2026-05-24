# Int64.Parse(string) 方法详解：C# 示例解析

> 原文：[https://www.geeksforgeeks.org/int64-parsestring-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-parsestring-method-in-c-sharp-with-examples/)

`Int64.Parse(string)` 方法用于将数字的字符串表示转换为其等效的 64 位有符号整数。

## 语法

```cs
public static long Parse (string str);
```

这里，`str` 是包含要转换的数字的字符串。`str` 的格式为 `[可选空格][可选符号]数字[可选空格]`。

## 返回值

返回一个 64 位有符号整数，相当于 `str` 中包含的数字。

## 异常

*   `ArgumentNullException`：如果 `str` 为 `null`。
*   `FormatException`：如果 `str` 格式不正确。
*   `OverflowException`：如果 `str` 代表小于 `Int64.MinValue` 或大于 `Int64.MaxValue` 的数字。

以下程序说明了上述方法的使用：

## 例 1

```cs
// C# program to demonstrate
// Int64.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // passing different values
        // to the method to check
        checkParse("9223372036854775807");
        checkParse("29,22337,20368547");
        checkParse("-922337203685477");
        checkParse(" 9223372075807");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {
        try {
            // declaring Int64 variable
            long val;

            // getting parsed value
            val = Int64.Parse(input);
            Console.WriteLine("'{0}' parsed as {1}", input, val);
        }
        catch (FormatException) {
            Console.WriteLine("Can't Parsed '{0}'", input);
        }
    }
}
```

## 输出

```cs
'9223372036854775807' parsed as 9223372036854775807
Can't Parsed '29,22337,20368547'
'-922337203685477' parsed as -922337203685477
' 9223372075807' parsed as 9223372075807
```

## 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// Int64.Parse(String) Method
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
        // declaring Int64 variable
        long val;

        // getting parsed value
        val = Int64.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

## 输出

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.int64.parse?view=netframework-4.7.2#System_Int64_Parse_System_String_](https://docs.microsoft.com/en-us/dotnet/api/system.int64.parse?view=netframework-4.7.2#System_Int64_Parse_System_String_)