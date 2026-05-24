# Single.ToString 方法 (C#) | Set-1

> 原文: [https://www.geeksforgeeks.org/single-tostring-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/single-tostring-method-in-c-sharp-set-1/)

`Single.ToString()` 方法用于将当前实例的数值转换为其等价的字符串表示形式。该方法的重载列表中有以下 4 种方法：

*   `ToString(String)`
*   `ToString()`
*   `ToString(IFormatProvider)`
*   `ToString(String, IFormatProvider)`

在这里，我们将讨论前两种方法。

## `ToString(String)` 方法

此方法用于使用指定的格式将当前实例的数值转换为其等效的字符串表示形式。

> **语法:** `public string ToString(string format);`
> 这里，它需要一个数字格式的字符串。
>
> **返回值:** 该方法返回当前实例值的字符串表示形式，由 `format` 指定。
>
> **异常:** 如果格式无效，此方法抛出 `FormatException`。

**例 1:**

```cs
// C# program to demonstrate the
// Single.ToString(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            float value = 565998.1564f;

            // Declaring and initializing format
            string s = "E04";

            // using the method
            string str = value.ToString(s);

            // Display the value
            Console.WriteLine("String value is {0}", str);
        }

        catch (FormatException e)
        {
            Console.WriteLine("Format is invalid.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
String value is 5.6600E+005
```

**例 2:** 为 `FormatException`

```cs
// C# program to demonstrate the
// Single.ToString(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value
            float value = 1623325.62412f;

            // Declaring and initializing format
            string s = "a";

            // using the method
            string str = value.ToString(s);

            // Display the value
            Console.WriteLine("String value is {0}", str);
        }

        catch (FormatException e)
        {
            Console.WriteLine("Format is invalid.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Format is invalid.
Exception Thrown: System.FormatException
```

## `ToString()` 方法

此方法用于将当前实例的数值转换为其等效的字符串表示形式。

> **语法:** `public override string ToString();`
>
> **返回值:** 这个方法返回一个代表这个实例值的字符串。

以下程序说明了 `Single.ToString()` 方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Single.ToString() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring and initializing value
        float value = 792759354.39503305f;

        // using ToString() method
        string res = value.ToString();

        // Display the value
        Console.WriteLine("String value is {0}", res);
    }
}
```

**Output:**

```cs
String value is 7.927594E+08
```

**例 2:**

```cs
// C# program to demonstrate the
// Single.ToString() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling get() method
        get(Single.MaxValue);
        get(Single.MinValue);
        get(40f);
        get(424967295.5858f);
    }

    // defining get() method
    public static void get(float value)
    {

        // using ToString() method
        string res = value.ToString();

        // Display the value
        Console.WriteLine("String value is {0}", res);
    }
}
```

**Output:**

```cs
String value is 3.402823E+38
String value is -3.402823E+38
String value is 40
String value is 4.249673E+08
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.single.tostring?view=netstandard-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.tostring?view=netstandard-2.1)