# C# | Uri。IsHexDigit()方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-ishexdigest-method/](https://www.geeksforgeeks.org/c-sharp-uri-ishexdigit-method/)

**乌利。IsHexDigit(Char)方法**用于判断指定字符是否为有效的十六进制数字。十六进制数字是数字 **0 到 9** 和字母 **A-F** 或 **a-f** 。

> **语法:**公共静态 bool IsHexDigit (char 字符)；
> 在这里，需要角色来验证。
> 
> **返回值:**如果字符是有效的十六进制数字，该方法返回*真*，否则返回假。

下面的程序说明了 *Uri 的使用。*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.IsHexDigit(Char) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing address1
        char ch = 'a';

        // Validating the Character
        // using IsHexDigit(Char) method
        bool value = Uri.IsHexDigit(ch);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is a valid Hexadecimal Digit", ch);
        else
            Console.WriteLine("{0} is a not valid Hexadecimal Digit", ch);
    }
}
```

**Output:**

```cs
a is a valid Hexadecimal Digit

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.IsHexDigit(Char) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get('a');
        get('.');
        get('1');
    }

    // defining get() method
    public static void get(char ch)
    {

        // Validating the Character
        // using IsHexDigit(Char) method
        bool value = Uri.IsHexDigit(ch);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is a valid Hexadecimal Digit", ch);
        else
            Console.WriteLine("{0} is a not valid Hexadecimal Digit", ch);
    }
}
```

**Output:**

```cs
a is a valid Hexadecimal Digit
. is a not valid Hexadecimal Digit
1 is a valid Hexadecimal Digit

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . ishexdigit？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.ishexdigit?view=netstandard-2.1)