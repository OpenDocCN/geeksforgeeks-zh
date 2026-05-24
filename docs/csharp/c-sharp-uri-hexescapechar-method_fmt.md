# C# | Uri.HexEscape(Char)方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-uri-hexescapechar-method/](https://www.geeksforgeeks.org/c-sharp-uri-hexescapechar-method/)

`Uri.HexEscape(Char)`方法用于将指定字符转换为其十六进制等价字符。

## 语法
```cs
public static string HexEscape (char character);
```
这里，`character`需要转换为十六进制表示。

## 返回值
这个方法返回指定字符的十六进制表示。

## 异常
如果`character`大于 255，此方法抛出`ArgumentOutOfRangeException`。

下面的程序说明了`Uri.HexEscape(Char)`方法的使用:

## 示例
```cs
// C# program to demonstrate the
// Uri.HexEscape() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing address1
        char ch = 'c';

        // Converting the specified character 
        // into its hexadecimal equivalent
        // using HexEscape() method
        string value = Uri.HexEscape(ch);

        // Displaying the result
        Console.WriteLine("Hexadecimal Equivalent is: {0}", value);
    }
}
```

## 输出
```cs
Hexadecimal Equivalent is: %63
```

## 注意
大于 255 的字符实际上是不可能的。

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.uri.hexescape?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.hexescape?view=netstandard-2.1)