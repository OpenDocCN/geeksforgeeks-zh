# C# | Uri。GetHashCode()方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-gethashcode-method/](https://www.geeksforgeeks.org/c-sharp-uri-gethashcode-method/)

**乌利。GetHashCode()方法**用于获取 URI 的哈希代码。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**该方法返回一个包含为此 URI 生成的哈希值的 Int32。

下面的程序说明了 *Uri 的使用。GetHashCode()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.GetHashCode() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing address1
        string address1 = "http://www.contoso.com/index.htm# search";

        // Getting HashCode by
        // using GetHashCode() method
        int value = address1.GetHashCode();

        // Displaying the result
        Console.WriteLine("HashCode is : {0}", value);
    }
}
```

**Output:**

```cs
HashCode is : 2065713268

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.GetHashCode() Method
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
    public static void get(Uri address1)
    {

        // Getting HashCode by
        // using GetHashCode() method
        int value = address1.GetHashCode();

        // Displaying the result
        Console.WriteLine("HashCode is : {0}", value);
    }
}
```

**Output:**

```cs
HashCode is : 2014
HashCode is : 1498

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . gethashcode？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.gethashcode?view=netstandard-2.1)