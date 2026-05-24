# C# | Uri。相等(对象)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-uri-equalsobject-method/](https://www.geeksforgeeks.org/c-sharp-uri-equalsobject-method/)

**乌利。Equals(Object)方法**用于比较两个 Uri 实例是否相等。

> **语法:**
> 公共覆盖 bool Equals(对象比较数)；
> 这里，它使用 Uri 实例或 URI 标识符与当前实例进行比较。
> 
> **返回值:**如果两个实例代表相同的 URI，则该方法返回布尔值 true，否则返回 false。

下面的程序说明了 *Uri 的使用。等于(对象)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.Equals(Object) Method
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

        // Comparing both instance
        // using CheckHostName() method
        bool value = address1.Equals(address2);

        // Displaying the result
        if (value)
            Console.WriteLine("address1 is Equals to address2");
        else
            Console.WriteLine("address1 is not Equals to address2");
    }
}
```

**Output:**

```cs
address1 is Equals to address2

```

**例 2:**

```cs
// C# program to demonstrate the
// Uri.Equals(Object) Method
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

        // Comparing both instance
        // using CheckHostName() method
        bool value = address1.Equals(address2);

        // Displaying the result
        if (value)
            Console.WriteLine("{0} is Equals to {1}", address1, address2);
        else
            Console.WriteLine("{0} is not Equals to {1}", address1, address2);
    }
}
```

**Output:**

```cs
http://www.contoso.com/ is Equals to http://www.contoso.com/
http://www.google.com/ is not Equals to http://www.facebook.com/

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . equals？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.equals?view=netstandard-2.1)