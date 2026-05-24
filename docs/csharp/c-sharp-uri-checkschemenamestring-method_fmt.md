# C# 中的 `Uri.CheckSchemeName(String)` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-uri-checkschemenamestring-method/](https://www.geeksforgeeks.org/c-sharp-uri-checkschemenamestring-method/)

`Uri.CheckSchemeName(String)` 方法用于判断指定的方案名称是否有效。

**语法：**
```csharp
public static bool CheckSchemeName(string schemeName);
```
这里需要 `schemeName` 参数进行验证。

**返回值：**
如果方案名称有效，则该方法返回布尔值 `true`，否则返回 `false`。

下面的程序说明了 `Uri.CheckSchemeName()` 方法的使用：

## 例 1

```cs
// C# program to demonstrate the
// Uri.CheckSchemeName(string) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing Uri
        Uri uri = new Uri("https://www.geeksforgeeks.org");

        // Determining the Scheme of the Uri
        string scheme = uri.Scheme;

        // using CheckSchemeName() method
        bool value = Uri.CheckSchemeName(scheme);

        // Displaying the result
        if (value)
            Console.WriteLine("Scheme name is valid");
        else
            Console.WriteLine("Scheme name is invalid");
    }
}
```

**输出：**
```cs
Scheme name is valid
```

## 例 2

```cs
// C# program to demonstrate the
// Uri.CheckSchemeName(string) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing Uri
        Uri uri = new Uri("https://www.pierobon.org/iis/review1.htm.html#one");

        // Determining the Scheme of the Uri
        string scheme = uri.Scheme;

        // using CheckSchemeName() method
        bool value = Uri.CheckSchemeName(scheme);

        // Displaying the result
        if (value)
            Console.WriteLine("Scheme name is valid");
        else
            Console.WriteLine("Scheme name is invalid");
    }
}
```

**输出：**
```cs
Scheme name is valid
```

**参考：**
*   [https://docs.microsoft.com/en-us/dotnet/api/system.uri.checkschemename?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.checkschemename?view=netstandard-2.1)