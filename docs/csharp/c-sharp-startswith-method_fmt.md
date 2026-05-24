# C# | StartsWith()方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-startswith-method/](https://www.geeksforgeeks.org/c-sharp-startswith-method/)

在 C# 中，`StartsWith()` 是一个字符串方法。此方法用于检查当前字符串实例的开头是否与指定的字符串匹配。如果匹配，则返回字符串，否则返回 `false`。使用 `foreach-loop`，可以检查许多字符串。通过向该方法传递不同类型和数量的参数，可以重载该方法。

## StartsWith(string) 方法

此方法用于检查字符串对象的开头是否与特定字符串匹配。如果匹配，则返回字符串，否则返回 `false`。

**语法：**

```cs
public bool StartsWith(string input_string)
```

**参数：**

> **input_string**：需要比较的字符串，该参数类型为 `System.String`。

**返回类型：** 该函数返回 `bool` 值，即 `true` 如果找到匹配，否则返回 `false`。返回类型为 `System.Boolean`。

以下是演示 `StartsWith(string)` 方法使用的程序：

*   **程序 1：**

```cs
// C# program to illustrate the
// String.StartsWith(String) Method
using System;

public class GFG {

    // Main Method
    static public void Main()
    {
        // The input string or character
        string str = "https://www.geeksforgeeks.org/placement-guide/";

        // Different string character and
        // Possible string to be matches
        string[] m = new string[] {
            "https://geeksforgeeks.org",
            "https://www.geeksforgeeks.org",
            "https://www.geeksforgeeks.org/placement"
        };

        // Using foreach - loop to check
        // each possible match
        foreach(string s in m)
        {
            // To check match second possibility
            if (str.StartsWith(s))
            {
                // Display the result
                Console.WriteLine(s);
                return;
            }
        }
    }
}
```

**输出：**

```cs
https://www.geeksforgeeks.org
```

*   **程序 2：**

```cs
// C# program to illustrate the
// String.StartsWith (String) Method
using System;

class Geeks
{
    // Main Method
    public static void Main()
    {
        string[] input_str = {
            "<p>GeekforGeeks Computer Science Portal </p>",
            "<h1>GeekforGeeks Sudo Placement </h1>",
            "<h2>GeekforGeeks Placement Preparation </h2>",
            "<h3>GeekforGeeks Contribute </h3>",
            "<h4>GeekforGeeks Contribute ",
            "<h5>GeekforGeeks Interview </h5>"
        };

        // Display result after implementation StartsWith()
        // method in strings starting to be tags removed.
        foreach(var n in input_str)
            Console.WriteLine(htmlStartTags(n));
    }

    private static string htmlStartTags(string str)
    {
        // To check starting "<"tag is or not
        if (str.Trim().StartsWith("<"))
        {
            // Find the closing ">" tag.
            int end = str.IndexOf(">");

            // After getting tag, then remove the tag
            if (end >= 0)
            {
                str = str.Substring(end + 1);

                // Additional starting tags to be remove
                str = htmlStartTags(str);
            }
        }
        return str;
    }
}
```

**输出：**

```cs
GeekforGeeks Computer Science Portal </p>
GeekforGeeks Sudo Placement </h1>
GeekforGeeks Placement Preparation </h2>
GeekforGeeks Contribute </h3>
GeekforGeeks Contribute 
GeekforGeeks Interview </h5>
```

**注：**

*   如果 `input_string` 为空，则该方法将给出 `ArgumentNullException`。
*   该方法还通过使用当前区域性执行区分大小写的和区分区域性的比较。

## StartsWith(string, bool, CultureInfo) 方法

当使用指定的区域性进行比较时，此方法用于检查当前字符串实例的开头是否与指定的字符串匹配。如果找到匹配项，则返回字符串，否则返回 `false`。

**语法：**

```cs
public bool StartsWith(string str,
                   bool case,
                   CultureInfo cul)
```

**参数：**

> **str**：是要比较的字符串，该参数的类型为 `System.String`。
> **case**：比较时置 `true` 忽略大小写，否则置 `false`，此参数类型为 `System.Boolean`。
> **cul**：是文化信息检查 `当前字符串` 和 `str` 是如何比较的。如果区域性为空，则使用当前区域性，该参数的类型为 `System.Globalization.CultureInfo`。

**返回值：** 该函数返回类型 `System.Boolean` 的值，如果 `str` 与当前字符串的开头匹配，则评估为 `true`，否则评估为 `false`。
**异常：** 如果 `str` 的值为空，则该方法将给出 `ArgumentNullException`。

**示例：**

```cs
// C# program to illustrate the
// String.StartsWith (string,
// bool, CultureInfo) Method
using System.Threading;
using System.Globalization;
using System;

class Sudo
{
    // Main Method
    public static void Main(string[] args)
    {
        // Input string
        string str1 = "Geeks";

        // Implementation of startswith() function

        // test in original string.
        bool result_a = str1.StartsWith("Geeks", false,
                         CultureInfo.InvariantCulture);

        // test in small letter string.
        bool result_b = str1.StartsWith("geeks", false,
                         CultureInfo.InvariantCulture);

        // test in capital letter string.
        bool result_c = str1.StartsWith("GEEKS", false,
                         CultureInfo.InvariantCulture);

        // test in no string parameter .
        bool result_d = str1.StartsWith(" ", false,
                     CultureInfo.InvariantCulture);

        // Display result
        Console.WriteLine(result_a);
        Console.WriteLine(result_b);
        Console.WriteLine(result_c);
        Console.WriteLine(result_d);
    }
}
```

**输出：**

```cs
True
False
False
False
```

## StartsWith(string, StringComparison) 方法

当使用指定的比较选项进行比较时，此方法用于检查当前字符串实例的开始是否与指定的字符串匹配。如果找到匹配项，则返回字符串，否则返回 `false`。

**语法：**

```cs
bool StartsWith(String str, StringComparison cType)
```

**参数：**

> **str**：是需要比较的字符串，该参数类型为 `System.String`。
> **cType**：它是决定当前字符串和 `str` 如何比较的枚举值之一。该参数类型为 `System.StringComparison`。

**返回值：** 该函数返回 `bool` 值，即 `true` 如果找到匹配，否则返回 `false`。返回类型为 `System.Boolean`。

**异常：**

*   如果 `str` 的值为空，则该方法将给出 `ArgumentNullException`。
*   如果 `cType` 的值不是 `StringComparison` 值，则此方法将给出 `ArgumentException`。

**示例：**

```cs
// C# program to illustrate the
// StartsWith(String, StringComparison)
// method
using System;

class Sudo
{
    // Main Method
    public static void Main(string[] args)
    {
        // Input two string
        string str1 = "GeeksforGeeks";
        string str2 = "Learn CSharp";

        // Implementation of startswith() function
        // test for original string1 value.
        bool result_a = str1.StartsWith("Geek",
              StringComparison.CurrentCulture);

        // test for small letter string1 value .
        bool result_b = str1.StartsWith("geek",
               StringComparison.CurrentCulture);

        // test for string2 value .
        bool result_tt = str2.StartsWith("CSharp",
                  StringComparison.CurrentCulture);

        bool result_t = str2.StartsWith("Learn",
               StringComparison.CurrentCulture);

        // Display result
        Console.WriteLine(result_a);
        Console.WriteLine(result_b);
        Console.WriteLine(result_tt);
        Console.WriteLine(result_t);
    }
}
```

**输出：**

```cs
True
False
False
True
```

**参考文献：**

*   [https://msdn.microsoft.com/en-us/library/baketxfw(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/baketxfw(v=vs.110).aspx)
*   [https://msdn.microsoft.com/en-us/library/6k0axhx9(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/6k0axhx9(v=vs.110).aspx)
*   [https://msdn.microsoft.com/en-us/library/ms131452(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/ms131452(v=vs.110).aspx)