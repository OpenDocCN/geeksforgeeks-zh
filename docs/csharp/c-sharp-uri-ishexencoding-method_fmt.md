# C# Uri.IsHexEncoding()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-uri-ishexencoding-method/](https://www.geeksforgeeks.org/c-sharp-uri-ishexencoding-method/)

## 方法介绍

`Uri.IsHexEncoding(String, Int32)`方法用于检查字符串中的字符是否为十六进制编码。这将检查字符串中遵循“`%hex`”模式的十六进制编码，其中“`hex`”是从 `0` 到 `9` 的数字或来自 `A-F`（不区分大小写）的字母。

## 语法

```cs
public static bool IsHexEncoding(string pattern, int index);
```

## 参数

- `pattern`: 是要检查的字符串。
- `index`: 是模式中检查十六进制编码的位置。

## 返回值

如果模式在指定位置是十六进制编码的，该方法返回的布尔值为 `true`，否则为 `false`。

## 示例

下面的程序说明了 `Uri.IsHexEncoding(String, Int32)` 方法的使用:

### 例 1

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
        // Declaring and initializing pattern
        string pattern = "%75";

        // Declaring and initializing index
        int index = 1;

        // Validating the Character in the String
        // using IsHexEncoding(String, Int32) Method
        bool value = Uri.IsHexEncoding(pattern, index);

        // Displaying the result
        if (value)
            Console.WriteLine("{0}({1}) is a valid " +
                     "Hexadecimal Encoded", pattern);
        else
            Console.WriteLine("{0} is a valid" +
              " Hexadecimal Encoded", pattern);
    }
}
```

**输出:**

```cs
%75 is a valid Hexadecimal Encoded
```

### 例 2

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
        // using IsHexEncoding(String, Int32) Method
        bool value = Uri.IsHexEncoding(pattern, index);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is a valid" +
              " Hexadecimal Encoded", pattern);
        else
            Console.WriteLine("{0} is a not valid" +
                  " Hexadecimal Encoded", pattern);
    }
}
```

**输出:**

```cs
%65 is a not valid Hexadecimal Encoded
%75 is a valid Hexadecimal Encoded
%55 is a valid Hexadecimal Encoded
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.uri.ishexencoding?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.ishexencoding?view=netstandard-2.1)