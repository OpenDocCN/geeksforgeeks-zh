# C# | Uri。擒纵数据串(串)法

> 原文:[https://www . geeksforgeeks . org/c-sharp-uri-擒纵数据字符串-method/](https://www.geeksforgeeks.org/c-sharp-uri-escapedatastringstring-method/)

**乌利。擒纵数据串(字符串)方法**用于将字符串转换为其转义表示。

> **语法:**公共静态字符串擒纵数据串(string string to scape)；
> 在这里，需要绳子才能逃脱。
> 
> **返回值:**这个方法返回一个包含*字符串的转义表示*的字符串。
> 
> **异常:**如果 stringToEscape 为空，这个方法抛出 **ArgumentNullException** 。
> 和 **UriFormatException** 如果*字符串的长度超过 32766 个字符。*

下面的程序说明了 *Uri 的使用。擒纵数据串(字符串)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// Uri.EscapeDataString(String) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing address1
            string address1 = "http://www.contoso.com/index.htm# search";

            // Converting a string to its 
            // escaped representation
            // using EscapeDataString() method
            string value = Uri.EscapeDataString(address1);

            // Displaying the result
            Console.WriteLine("Escaped string is : {0}", value);
        }

        catch (ArgumentNullException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Escaped string is : http%3A%2F%2Fwww.contoso.com%2Findex.htm%23search

```

**示例 2:** 适用于**参数异常**

```cs
// C# program to demonstrate the
// Uri.EscapeDataString(String) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Declaring and initializing address1
            string address1 = null;

            // Converting a string to its 
            // escaped representation
            // using EscapeDataString() method
            string value = Uri.EscapeDataString(address1);

            // Displaying the result
            Console.WriteLine("Escaped string is : {0}", value);
        }

        catch (ArgumentNullException e) 
        {
            Console.WriteLine("stringToEscape can not be null");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (UriFormatException e) 
        {
            Console.WriteLine("Length of stringToEscape should"+
                          " not exceed from 32766 characters.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
stringToEscape can not be null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为**尿酸异常**

```cs
// C# program to demonstrate the
// Uri.EscapeDataString(String) Method
using System;
using System.Text;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing address1
            StringBuilder address1 = new StringBuilder("http://www.contoso.com/index.htm# search");

            // appending StringBuilder
            for (int i = 1; i <= 3000; i++)
                address1.Append("abcedfghijklmnopdjdjdjdjdjjddjjdjdj");

            // Converting a string to its 
            // escaped representation
            // using EscapeDataString() method
            string value = Uri.EscapeDataString(address1.ToString());

            // Displaying the result
            Console.WriteLine("Escaped string is : {0}", value);
        }

        catch (ArgumentNullException e)
       {
            Console.WriteLine("stringToEscape can not be null");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (UriFormatException e)
        {
            Console.WriteLine("Length of stringToEscape should"+
                          " not exceed from 32766 characters.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Length of stringToEscape should not exceed from 32766 characters.
Exception Thrown: System.UriFormatException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uri . escape datastring？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.escapedatastring?view=netstandard-2.1)