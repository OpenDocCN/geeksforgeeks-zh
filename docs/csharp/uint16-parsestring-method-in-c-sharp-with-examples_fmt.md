# UInt16.Parse(String)方法详解

> 原文：[https://www.geeksforgeeks.org/uint16-parsestring-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-parsestring-method-in-c-sharp-with-examples/)

`UInt16.Parse(String)`方法用于将数字的字符串表示转换为其等效的16位无符号整数。

## 语法

```cs
public static ushort Parse (string str);
```

这里，`str`是包含要转换的数字的字符串。`str`的格式为`【可选空格】【可选符号】数字【可选空格】`。这个符号可以是正的，也可以是负的。但是负号只能和零一起使用，否则会抛出`OverflowException`。

## 返回值

返回一个16位无符号整数，相当于`str`中包含的数字。

## 异常

*   `ArgumentNullException`：如果`str`为`null`。
*   `FormatException`：如果`str`格式不正确。
*   `OverflowException`：如果`str`代表小于`UInt16.MinValue`或大于`UInt16.MaxValue`的数字。

## 示例

以下程序说明了上述方法的使用：

### 示例 1

```cs
// C# program to demonstrate
// UInt16.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // passing different values
        // to the method to check
        checkParse("65535");
        checkParse("15,784");
        checkParse("-4589");
        checkParse(" 785");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {
        try {
            // declaring UInt16 variable
            ushort val;

            // getting parsed value
            val = UInt16.Parse(input);
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

**输出：**

```cs
'65535' parsed as 65535
Can't Parsed '15,784'
Can't Parsed '-4589'
' 785' parsed as 785
```

### 示例 2：适用于`ArgumentNullException`

```cs
// C# program to demonstrate
// UInt16.Parse(String) Method
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
        // declaring UInt16 variable
        ushort val;

        // getting parsed value
        val = UInt16.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**输出：**

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint16.parse?view=netframework-4.7.2#System_UInt16_Parse_System_String_](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.parse?view=netframework-4.7.2#System_UInt16_Parse_System_String_)