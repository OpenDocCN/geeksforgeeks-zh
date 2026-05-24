# C# | Uri。IsBaseOf(Uri)方法

> 原文:[https://www . geesforgeks . org/c-sharp-uri-isbaseofuri-method/](https://www.geeksforgeeks.org/c-sharp-uri-isbaseofuri-method/)

**乌利。IsBaseOf(Uri)方法**用于确定当前 Ui 实例是否是指定 Ui 实例的基。

> **语法:**public bool IsBaseOf(Uri Uri)；
> 这里，需要指定的 Uri 实例来测试。
> **返回值:**如果当前 uri 实例是 Uri 的基，则该方法返回 *true* ，否则返回 false。
> **异常:**如果 *uri* 为空，此方法抛出 **ArgumentNullException** 。

下面的程序说明了 *Uri 的使用。【方法:
**例 1:*** 

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Uri.IsBaseOf(Uri) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing address1
        Uri address1 = new Uri("http://www.contoso.com/index.htm# search");

        // Declaring and initializing address2
        Uri address2 = new Uri("http://www.contoso.com/index.htm");

        // using IsBaseOf() method
        bool value = address1.IsBaseOf(address2);

        // Displaying the result
        if (value)
            Console.WriteLine("address1 instance is a base"+
                              " of the specified address2");
        else
            Console.WriteLine("address1 instance is not a "+
                          "base of the specified address2");
    }
}
```

**Output:** 

```cs
address1 instance is a base of the specified address2
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Uri.IsBaseOf(Uri) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get(new Uri("http://www.contoso.com"),
           new Uri("http://www.contoso.com"));

        get(new Uri("http://www.google.com"),
         new Uri("http://www.facebook.com"));
    }

    // defining get() method
    public static void get(Uri address1,
                           Uri address2)
    {

        // using IsBaseOf() method
        bool value = address1.IsBaseOf(address2);

        // Displaying the result
        if (value)
            Console.WriteLine("address1 instance is a "+
                      "base of the specified address2");
        else
            Console.WriteLine("address1 instance is "+
              "not a base of the specified address2");
    }
}
```

**Output:** 

```cs
address1 instance is a base of the specified address2
address1 instance is not a base of the specified address2
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . is baseof？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.isbaseof?view=netstandard-2.1)