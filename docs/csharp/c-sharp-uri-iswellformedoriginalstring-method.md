# C# | Uri。IsWellFormedOriginalString()方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-iswellformedoriginalstring-method/](https://www.geeksforgeeks.org/c-sharp-uri-iswellformedoriginalstring-method/)

**乌利。IsWellFormedOriginalString()方法**用于显示用于构造此 Uri 的字符串是否格式良好，不需要进一步转义。

> **语法:**公共 bool is wellformicrosoldstring()；
> 
> **返回值:**如果字符串格式良好，该方法返回真，否则返回假。

下面的程序说明了 *Uri 的使用。iswellformedoriginarstring()*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.IsWellFormedOriginalString()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing address
        Uri address1 = new Uri("http://www.contoso.com/index.htm# search");

        // Validating if Uri is well formed or not
        // using IsWellFormedOriginalString() method
        bool value = address1.IsWellFormedOriginalString();

        // Displaying the result
        if (value)
            Console.WriteLine("uri is well formed");
        else
            Console.WriteLine("uri is not well formed");
    }
}
```

**Output:**

```cs
uri is well formed

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.IsWellFormedOriginalString() 
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // calling get() method
            get(new Uri("http://www.contoso.com/path"));

            // if The string is not correctly escaped.
            get(new Uri("http://www.contoso.com/path???/file name"));

            // The string is an absolute Uri 
            // that represents an implicit 
            // file Uri.
            get(new Uri("c:\\directory\filename"));

            // The string is an absolute URI that
            // is missing a slash before the path.
            get(new Uri("file://c:/directory/filename"));

            // The parser for the Uri.Scheme indicates 
            // that the original string was not well-formed.
            get(new Uri("xy11.z://www.contoso.com/path/file"));

            // The string contains unescaped backslashes
            // even if they are treated as forwarding slashes.
            get(new Uri("http:\\host/path/file")); 

            // The string represents a hierarchical 
            // absolute Uri and does not contain "://".
            get(new Uri("www.contoso.com/path/file"));
        }

        catch (UriFormatException e) 
        {
            Console.Write("uri is so poorly formed that system thrown ");
            Console.Write("{0}", e.GetType(), e.Message);
            Environment.Exit(1);
        }
    }

    // defining get() method
    public static void get(Uri address)
    {
        // Validating if Uri is well formed or not
        // using IsWellFormedOriginalString() method
        bool value = address.IsWellFormedOriginalString();

        // Displaying the result
        if (value)
            Console.WriteLine("uri is well formed");
        else
            Console.WriteLine("uri is poorly formed");
    }
}
```

**Output:**

```cs
uri is well formed
uri is poorly formed
uri is poorly formed
uri is poorly formed
uri is well formed
uri is so poorly formed that system thrown System.UriFormatException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . iswellformedoriginarstring？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.iswellformedoriginalstring?view=netstandard-2.1)