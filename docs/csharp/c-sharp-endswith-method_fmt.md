# C# | EndsWith()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-endswith-method/](https://www.geeksforgeeks.org/c-sharp-endswith-method/)

在 C# 中，`EndsWith()` 是一个字符串方法。此方法用于检查当前字符串实例的结尾是否与指定的字符串匹配。如果匹配，则返回字符串，否则返回 false。使用 `foreach` 循环，可以检查许多字符串。通过向该方法传递不同类型和数量的参数，可以重载该方法。

*   `String.EndsWith(String)` 方法
*   `String.EndsWith(String, Boolean, CultureInfo)` 方法
*   `String.EndsWith(String, StringComparison)` 方法

### String.EndsWith(String) 方法

此方法用于检查字符串对象的结尾是否与特定字符串匹配。如果匹配，则返回字符串，否则返回 false。

**语法:**

```cs
public bool EndsWith(string input_string)
```

**参数:**

> **input_string**: 需要比较的字符串，该参数类型为 `System.String`。

**返回类型:** 该函数返回 `Boolean` 值，即 `true` 如果找到匹配，否则返回 `false`。返回类型为 `System.Boolean`。

以下是演示 `String.EndsWith(String)` 方法使用的程序:

*   **程序 1:**

```cs
// C# program to illustrate the
// String.EndsWith(String) Method
using System;

public class GFG {

    // Main Method
    static public void Main()
    {

        // Input two string
        string str1 = "Sudo Placement++";
        string str2 = "Sudo Placement++";
        bool x, y;

        // Implement EndsWith() method
        x = str1.EndsWith("++");
        y = str2.EndsWith("--");

        // Return  match string "True"
        Console.WriteLine(x.ToString());

        // Return no match string "False"
        Console.WriteLine(y.ToString());
    }
}
```

**Output:**

```cs
True
False
```

*   **程序 2:**

```cs
// C# program to illustrate the
// String.EndsWith (String) Method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Html ending  tag (</) will be remove
        // then print the result
        string[] input_str = {
            "<p> GeekforGeeks Computer Science Portal </p>",
            "<h1> GeekforGeeks Sudo Placement </h1>",
            "<h2> GeekforGeeks Placement Preparation </h2>",
            "<h3> GeekforGeeks Contribute </h3>",
            "<h4> GeekforGeeks Contribute ",
            "<h> GeekforGeeks Interview </h>",
        };

        // Display result after implementation EndsWith()
        // method in strings  ending tag  to be  removed.
        foreach(var n in input_str)
            Console.WriteLine(htmlEndTags(n));
    }

    private static string htmlEndTags(string str)
    {

        // set found false
        bool found = false;

        // To check ending tag to be found or not
        if (str.Trim().EndsWith(">")) {

            // To search  opening tag
            int end = str.LastIndexOf("</");

            // if got ending tag then remove
            if (end >= 0) {

                // found set become True
                found = true;

                // update string
                str = str.Substring(0, end);
            }
        }

        // if found to be true then
        // return after removing string
        if (found)
            str = htmlEndTags(str);

        return str;
    }
}
```

![](img/ca22615d30cbbccdf27aec9b92d5ce99.png)

**注:**

*   如果 `input_string` 为空，则该方法将给出 `ArgumentNullException`。
*   该方法还通过使用当前区域性执行区分大小写的和区分区域性的比较。

### String.EndsWith(String, Boolean, CultureInfo) 方法

当使用指定的区域性进行比较时，此方法用于检查当前字符串实例的结尾是否与指定的字符串匹配。如果找到匹配，则返回字符串，否则返回 false。

**语法:**

```cs
public bool EndsWith(string str,
                   bool case,
                   CultureInfo cul)
```

**参数:**

> **str:** 是要比较的字符串，该参数的类型为 `System.String`。
> **ignoreCase:** 比较时置 `true` 忽略大小写，否则置 `false`，此参数类型为 `System.Boolean`。
> **culture:** 是文化信息检查 `当前字符串` 和 `str` 是如何比较的。如果区域性为空，则使用当前区域性，该参数的类型为 `System.Globalization.CultureInfo`。

**返回值:** 该函数返回类型 `System.Boolean` 的值，如果 `str` 与当前字符串的结尾匹配，则评估为 `true`，否则评估为 `false`。

**异常:** 如果 `str` 的值为空，则该方法将给出 `ArgumentNullException`。

**例:**

```cs
// C# program to illustrate the
// String.EndsWith() (string,
// bool, CultureInfo) Method
using System.Threading;
using System.Globalization;
using System;

class StringStartWith {

    // Main Method
    public static void Main(string[] args)
    {

        // Input string
        string str1 = "Geeksforgeeks";
        string str2 = "SudoPlacement ";

        // Implementation of Endswith() function
        // test for original string
        bool result_a = str1.EndsWith("Geeks", false,
                       CultureInfo.InvariantCulture);

        // test for small letter string
        bool result_b = str1.EndsWith("geeks", false,
                        CultureInfo.InvariantCulture);

        // test for capital letter string
        bool result_c = str1.EndsWith("GEEKS", false,
                       CultureInfo.InvariantCulture);

        // test in no string parameter
        bool result_d = str1.EndsWith(" ", false,
                    CultureInfo.InvariantCulture);

        // test for strin2 argument .
        bool result_x = str2.EndsWith("Sudo", false,
                       CultureInfo.InvariantCulture);

        // Display result
        Console.WriteLine(result_a);
        Console.WriteLine(result_b);
        Console.WriteLine(result_c);
        Console.WriteLine(result_d);
        Console.WriteLine(result_x);
    }
}
```

**Output:**

```cs
False
True
False
False
False
```

### String.EndsWith(String, StringComparison) 方法

使用指定的比较选项进行比较时，此方法用于检查当前字符串实例的结尾是否与指定的字符串匹配。如果找到匹配，则返回字符串，否则返回 false。

**语法:**

```cs
bool EndsWith(String str, StringComparison cType)
```

**参数:**

> **str:** 是需要比较的字符串，该参数类型为 `System.String`。
> **cType:** 它是决定当前字符串和 `str` 如何比较的枚举值之一。该参数类型为 `System.StringComparison`。

**返回值:** 该函数返回 `Boolean` 值，即 `true` 如果找到匹配，否则返回 `false`。返回类型为 `System.Boolean`。

**例外:**

*   如果 `str` 的值为空，则该方法将给出 `ArgumentNullException`。
*   如果 `cType` 的值不是 `StringComparison` 值，则此方法将给出 `ArgumentException`。

**例:**

```cs
// C# program to illustrate the
// EndsWith(String, StringComparison)
// method
using System;

class Sudo {

    // Main Method
    public static void Main(string[] args)
    {

        // Input two string
        string str1 = "GeeksforGeeks";
        string str2 = "Sudo Placement";
        string str3 = "Geeks Article";

        // Implementation of startswith() function
        // test for original string1 value.
        bool result_a = str1.EndsWith("Geek",
            StringComparison.CurrentCulture);

        // test for small letter string1 value .
        bool result_b = str1.EndsWith("geek",
            StringComparison.CurrentCulture);

        // test for string2 value .
        bool result_tt = str2.EndsWith("Placement",
                    StringComparison.CurrentCulture);

        bool result_t = str2.EndsWith("Sudo",
            StringComparison.CurrentCulture);

        // test for string3 value .
        bool result_x = str3.EndsWith("Article",
                StringComparison.CurrentCulture);

        bool result_xx = str3.EndsWith("Geeks",
               StringComparison.CurrentCulture);

        // Display result
        Console.WriteLine(result_a);
        Console.WriteLine(result_b);
        Console.WriteLine(result_tt);
        Console.WriteLine(result_t);
        Console.WriteLine(result_x);
        Console.WriteLine(result_xx);
    }
}
```

**Output:**

```cs
False
False
True
False
True
False
```

**参考:** [https://docs.microsoft.com/en-us/dotnet/api/system.string.endswith?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.string.endswith?view=netframework-4.7.2)