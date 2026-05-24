# C# Uri.EscapeDataString(String) 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-uri-escapedatastringstring-method/](https://www.geeksforgeeks.org/c-sharp-uri-escapedatastringstring-method/)

`Uri.EscapeDataString(String)` 方法用于将字符串转换为其转义表示。

## 语法

```csharp
public static string EscapeDataString(string stringToEscape);
```
这里，`stringToEscape` 是需要转义的字符串。

## 返回值

此方法返回一个包含 `stringToEscape` 转义表示的字符串。

## 异常

- 如果 `stringToEscape` 为 `null`，此方法将抛出 `ArgumentNullException`。
- 如果 `stringToEscape` 的长度超过 32766 个字符，将抛出 `UriFormatException`。

## 示例

下面的程序说明了 `Uri.EscapeDataString(String)` 方法的使用：

### 示例 1

```csharp
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
            string address1 = "http://www.contoso.com/index.htm#search";

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

**输出:**

```csharp
Escaped string is : http%3A%2F%2Fwww.contoso.com%2Findex.htm%23search
```

### 示例 2：处理 `ArgumentNullException`

```csharp
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
            Console.WriteLine("Length of stringToEscape should" +
                              " not exceed from 32766 characters.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```csharp
stringToEscape can not be null
Exception Thrown: System.ArgumentNullException
```

### 示例 3：处理 `UriFormatException`

```csharp
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
            StringBuilder address1 = new StringBuilder("http://www.contoso.com/index.htm#search");

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
            Console.WriteLine("Length of stringToEscape should" +
                              " not exceed from 32766 characters.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```csharp
Length of stringToEscape should not exceed from 32766 characters.
Exception Thrown: System.UriFormatException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.uri.escapedatastring?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uri.escapedatastring?view=netstandard-2.1)