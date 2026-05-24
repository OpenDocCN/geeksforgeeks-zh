# C# | Uri。CheckSchemeName(字符串)方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-checkschemnamestring-method/](https://www.geeksforgeeks.org/c-sharp-uri-checkschemenamestring-method/)

**乌利。CheckSchemeName(String)方法**用于判断指定的方案名称是否有效。

> **语法:**公共静态 bool CheckSchemeName(字符串 scheme name)；
> 这里需要方案名进行验证。
> 
> **返回值:**如果方案名称有效，则该方法返回布尔值 *true* ，否则返回 false。

下面的程序说明了 *Uri 的使用。CheckSchemeName()* 方法:

**例 1:**

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

**Output:**

```cs
Scheme name is valid

```

**例 2:**

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
        Uri uri = new Uri("https://www.pierobon.org/iis/review1.htm.html# one");

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

**Output:**

```cs
Scheme name is valid

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . checkscheme name？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.checkschemename?view=netstandard-2.1)