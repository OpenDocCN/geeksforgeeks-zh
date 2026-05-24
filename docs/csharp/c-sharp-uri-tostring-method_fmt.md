# C# | Uri.ToString() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-uri-tostring-method/](https://www.geeksforgeeks.org/c-sharp-uri-tostring-method/)

## 方法说明

`Uri.HexEscape(Char)` 方法用于获取指定 `Uri` 实例的规范字符串表示。

### 语法

```cs
public override string ToString();
```

### 返回值

此方法返回一个包含 `Uri` 实例的非转义规范表示的 `string` 实例。除了 `#`、`?` 和 `%` 外，所有字符都不会被转义。

下面的程序说明了 `Uri.ToString()` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// Uri.ToString() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Create a new Uri from a string address.
        Uri uri = new Uri("HTTP://www.Contoso.com:80/thick%20and%20thin.htm");

        // Converts a specified uri into
        // its string equivalent.
        // using ToString() method
        string value = uri.ToString();

        // Displaying the result
        Console.WriteLine("Converted string is: {0}", value);
    }
}
```

**输出：**

```cs
Converted string is: http://www.contoso.com/thick and thin.htm
```

### 示例 2

```cs
// C# program to demonstrate the
// Uri.ToString() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(new Uri("http://www.contoso.com"));
        get(new Uri("http://www.google.com"));
    }

    // defining get() method
    public static void get(Uri uri)
    {
        // Converts a specified uri 
        // into its string equivalent.
        // using ToString() method
        string value = uri.ToString();

        // Displaying the result
        Console.WriteLine("Converted string is: {0}", value);
    }
}
```

**输出：**

```cs
Converted string is: http://www.contoso.com/
Converted string is: http://www.google.com/
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uri.tostring?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.tostring?view=netstandard-2.1)