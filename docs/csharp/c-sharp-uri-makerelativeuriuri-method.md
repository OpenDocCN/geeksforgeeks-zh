# C# | Uri。make relative euri(Uri)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-uri-maker relativeeuriuri-method/](https://www.geeksforgeeks.org/c-sharp-uri-makerelativeuriuri-method/)

**乌利。maker relative euri(Uri)方法**用于确定两个 Uri 实例之间的差异。

> **语法:**public Uri maker relative Uri(Uri)；
> 在这里，要把 URI 比作现在的 URI。
> 
> **返回值:**如果这个 Uri 实例和 *uri* 的主机名和方案相同，那么这个方法返回一个相对 uri，当追加到当前 URI 实例时，产生 *uri* 。如果主机名或方案不同，那么这个方法返回一个代表 *uri* 参数的 Uri。

**异常:**

*   **ArgumentNullException:** 如果 uri 为空。
*   **UriFormatException:** 如果此实例表示相对 URI，并且此属性仅对绝对 URIs 有效。

下面的程序说明了 *Uri 的使用。make relative euri(Uri)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.MakeRelativeUri() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Create a base Uri.
        Uri address1 = new Uri("http://www.contoso.com/");

        // Create a new Uri from a string.
        Uri address2 = new Uri("http://www.contoso.com/index.htm?date=today");

        // Determining the difference 
        // between address1 and address2.
        // using MakeRelativeUri() method

        Uri uri = address1.MakeRelativeUri(address2);

        // Displaying the result
        Console.WriteLine("relative uri is : {0}", uri);
    }
}
```

**Output:**

```cs
relative uri is : index.htm?date=today

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// Uri.MakeRelativeUri() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Create a base Uri.
            Uri address1 = new Uri("http://www.contoso.com/");

            // Create a new Uri from a string.
            Uri address2 = null;

            // Determining the difference 
            // between address1 and address2.
            // using MakeRelativeUri() method
            Uri uri = address1.MakeRelativeUri(address2);

            // Displaying the result
            Console.WriteLine("relative uri is : {0}", uri);
        }

        catch (ArgumentNullException e) 
        {
            Console.WriteLine("uri should not be null");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
uri should not be null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为*尿酸异常*

```cs
// C# program to demonstrate the
// Uri.MakeRelativeUri() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Create a base Uri.
            Uri address1 = new Uri("http://www.contoso.com/");

            // Determining the difference
            // between address1 and address2.
            // using MakeRelativeUri() method

            Uri uri = address1.MakeRelativeUri(new Uri("http:://www.contoso.com/??index.htm?date=today"));

            // Displaying the result
            Console.WriteLine("relative uri is : {0}", uri);
        }
        catch (ArgumentNullException e) {
            Console.WriteLine("uri should not be null");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (UriFormatException e) {
            Console.WriteLine("uri should be in correct format");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
uri should be in correct format
Exception Thrown: System.UriFormatException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . maker relative euri？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.makerelativeuri?view=netstandard-2.1)