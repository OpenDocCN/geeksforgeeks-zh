# Int32.Parse(String) 方法详解

> 原文：[https://www.geeksforgeeks.org/int32-parsestring-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-parsestring-method-in-c-sharp-with-examples/)

`Int32.Parse(String)` 方法用于将数字的字符串表示转换为其等效的 32 位有符号整数。

## 语法

```cs
public static int Parse (string str);
```

这里，`str` 是包含要转换的数字的字符串。`str` 的格式为 `[可选空格][可选符号]数字[可选空格]`。

## 返回值

返回一个 32 位有符号整数，相当于 `str` 中包含的数字。

## 异常

*   `ArgumentNullException`：如果 `str` 为 `null`。
*   `FormatException`：如果 `str` 格式不正确。
*   `OverflowException`：如果 `str` 代表小于 `Int32.MinValue` 或大于 `Int32.MaxValue` 的数字。

以下程序说明了上述方法的使用：

## 示例 1

```cs
// C# program to demonstrate
// Int32.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // passing different values
        // to the method to check
        checkParse("2147483647");
        checkParse("214,7483,647");
        checkParse("-2147483");
        checkParse(" 2183647 ");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {
        try {
            // declaring Int32 variable
            int val;

            // getting parsed value
            val = Int32.Parse(input);
            Console.WriteLine("'{0}' parsed as {1}", input, val);
        }
        catch (FormatException) {
            Console.WriteLine("Can't Parsed '{0}'", input);
        }
    }
}
```

**输出：**

```cs
'2147483647' parsed as 2147483647
Can't Parsed '214,7483,647'
'-2147483' parsed as -2147483
' 2183647 ' parsed as 2183647
```

## 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// Int32.Parse(String) Method
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
        // declaring Int32 variable
        int val;

        // getting parsed value
        val = Int32.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**输出：**

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.int32.parse?view=netframework-4.7.2#System_Int32_Parse_System_String_](https://docs.microsoft.com/en-us/dotnet/api/system.int32.parse?view=netframework-4.7.2#System_Int32_Parse_System_String_)