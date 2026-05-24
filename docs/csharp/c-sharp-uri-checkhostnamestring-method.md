# C# | Uri。检查主机名(字符串)方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-checkhostnamestring-method/](https://www.geeksforgeeks.org/c-sharp-uri-checkhostnamestring-method/)

**乌利。检查主机名(字符串)方法**用于确定指定的主机名是否是有效的域名。

> **语法:**公共静态 UriHostNameType CheckHostName(字符串名称)；
> 这里，需要主机名来验证。这可以是 IPv4 或 IPv6 地址或互联网主机名。
> 
> **返回值:**该方法返回一个 **UriHostNameType** ，表示主机名的类型。如果无法确定主机名的类型，或者主机名为空或零长度字符串，则该方法返回*未知*。

下面的程序说明了 *Uri 的使用。检查主机名()*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.CheckHostName(string) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing uri
        string uri = "www.geeksforgeeks.org";

        // using CheckHostName() method
        UriHostNameType value = Uri.CheckHostName(uri);

        // Displaying the result
        Console.WriteLine("Host type is: {0}", value);
    }
}
```

**Output:**

```cs
Host type is: Dns

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.CheckHostName(string) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing uri
        string uri = "http:// localhost:3000";

        // using CheckHostName() method
        UriHostNameType value = Uri.CheckHostName(uri);

        // Displaying the result
        Console.WriteLine("Host type is: {0}", value);
    }
}
```

**Output:**

```cs
Host type is: Unknown

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . check hostname？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.checkhostname?view=netstandard-2.1)