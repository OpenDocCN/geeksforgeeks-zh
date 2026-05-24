# C# | Uri。IsHexEncoding()方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-ishexencoding-method/](https://www.geeksforgeeks.org/c-sharp-uri-ishexencoding-method/)

**乌利。IsHexEncoding(String，Int32)方法**用于检查字符串中的字符是否为十六进制编码。这将检查字符串中遵循“*%十六进制*”模式的十六进制编码，其中“*十六进制*”是从 *0 到 9* 的数字或来自 *A-F(不区分大小写)*的字母。

> **语法:**公共静态 bool IsHexEncoding(字符串模式，int 索引)；
> 
> **参数:**
> **图案**:是要检查的弦。
> **索引**:是模式中检查十六进制编码的位置。
> 
> **返回值:**如果模式在指定位置是十六进制编码的，该方法返回的布尔值为*真*，否则为*假*。

下面的程序说明了 *Uri 的使用。IsHexEncoding(String，Int32)* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.IsHexEncoding(String,
// Int32)  Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing pattern
        string pattern = "%75";

        // Declaring and initializing index
        int index = 1;

        // Validating the Character in the String
        // using IsHexEncoding(String, Int32)  method
        bool value = Uri.IsHexEncoding(pattern, index);

        // Displaying the result
        if (value)
            Console.WriteLine("{0}({1}) is a valid "+
                     "Hexadecimal Encoded", pattern);
        else
            Console.WriteLine("{0} is a valid"+
              " Hexadecimal Encoded", pattern);
    }
}
```

**Output:**

```cs
%75 is a valid Hexadecimal Encoded

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.IsHexEncoding(String, 
// Int32) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get("%65", 1);
        get("%75", 0);
        get("%55", 0);
    }

    // defining get() method
    public static void get(string pattern, 
                                int index)
    {

        // Validating the Character in the String
        // using IsHexEncoding(String, Int32)  method
        bool value = Uri.IsHexEncoding(pattern, index);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is a valid"+
              " Hexadecimal Encoded", pattern);
        else
            Console.WriteLine("{0} is a not valid"+
                  " Hexadecimal Encoded", pattern);
    }
}
```

**Output:**

```cs
%65 is a not valid Hexadecimal Encoded
%75 is a valid Hexadecimal Encoded
%55 is a valid Hexadecimal Encoded

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . ishexencoding？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.ishexencoding?view=netstandard-2.1)