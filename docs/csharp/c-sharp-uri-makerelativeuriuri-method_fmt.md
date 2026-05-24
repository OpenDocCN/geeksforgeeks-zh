# C# | Uri.MakeRelativeUri(Uri)方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-uri-makerelativeuriuri-method/](https://www.geeksforgeeks.org/c-sharp-uri-makerelativeuriuri-method/)

`Uri.MakeRelativeUri(Uri)`方法用于确定两个`Uri`实例之间的差异。

> **语法：** `public Uri MakeRelativeUri(Uri uri);`
> 在这里，`uri`是要与当前`Uri`实例进行比较的`Uri`。
>
> **返回值：** 如果这个`Uri`实例和`uri`的主机名和方案相同，那么这个方法返回一个相对`Uri`，当追加到当前`Uri`实例时，产生`uri`。如果主机名或方案不同，那么这个方法返回一个代表`uri`参数的`Uri`。

**异常：**

*   `ArgumentNullException`： 如果`uri`为空。
*   `UriFormatException`： 如果此实例表示相对 URI，并且此属性仅对绝对 URI 有效。

下面的程序说明了`Uri.MakeRelativeUri(Uri)`方法的使用：

**例 1：**

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

**Output：**

```cs
relative uri is : index.htm?date=today
```

**示例 2：** 适用于`ArgumentNullException`

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

**Output：**

```cs
uri should not be null
Exception Thrown: System.ArgumentNullException
```

**例 3：** 为`UriFormatException`

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

**Output：**

```cs
uri should be in correct format
Exception Thrown: System.UriFormatException
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uri.makerelativeuri?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.makerelativeuri?view=netstandard-2.1)