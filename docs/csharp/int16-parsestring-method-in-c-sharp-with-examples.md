# Int16。用例子解析 C# 中的(字符串)方法

> 原文:[https://www . geesforgeks . org/int 16-parse string-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-parsestring-method-in-c-sharp-with-examples/)

**Int16。解析(字符串)方法**用于将数字的字符串表示转换为其等效的 16 位有符号整数。

**语法:**

```cs
public static short Parse (string str);
```

这里，*字符串*是包含要转换的数字的字符串。*字符串*的格式为*【可选空格】【可选符号】数字【可选空格】*。

**返回值:**是一个 16 位有符号整数，相当于*字符串*中包含的数字。

**异常:**

*   **参数空异常**:如果*字符串*为空。
*   **格式异常**:如果*字符串*格式不正确。
*   **overoverowexception**:如果 *str* 代表小于*T5】MinValueT7】或大于*T9】MaxValueT11】的数字。**

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate
// Int16.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // passing different values
        // to the method to check
        checkParse("14321");
        checkParse("15,784");
        checkParse("-4589");
        checkParse(" 456");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {

        try {

            // declaring Int16 variable
            short val;

            // getting parsed value
            val = Int16.Parse(input);
            Console.WriteLine("'{0}' parsed as {1}", input, val);
        }

        catch (FormatException) 
        {
            Console.WriteLine("Can't Parsed '{0}'", input);
        }
    }
}
```

**Output:**

```cs
'14321' parsed as 14321
Can't Parsed '15,784'
'-4589' parsed as -4589
' 456' parsed as 456

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// Int16.Parse(String) Method
// for ArgumentNullException
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // passing null value as a input
            checkParse(null);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining checkparse method
    public static void checkParse(string input)
    {

        // declaring Int16 variable
        short val;

        // getting parsed value
        val = Int16.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . parse？view = net framework-4 . 7 . 2 # System _ int 16 _ Parse _ System _ String _](https://docs.microsoft.com/en-us/dotnet/api/system.int16.parse?view=netframework-4.7.2# System_Int16_Parse_System_String_)