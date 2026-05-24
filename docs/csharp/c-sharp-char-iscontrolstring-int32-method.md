# C# | Char。IsControl(字符串，Int32)方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-is control string-int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-iscontrolstring-int32-method/)

此方法用于指示指定字符串中指定位置的字符是否被归类为控制字符。

**语法:**

```cs
public static bool IsControl (string s, int index);
```

**参数:**

> **s** :是弦。
> 
> **索引**:是 *s* 中的人物位置。

**返回值:**如果 *s* 中位置*索引*的字符是控制字符，则该方法返回*真*，否则返回*假*。

**异常:**

*   **参数空异常:**如果 *s* 为空。
*   **argumentout of range 异常:**如果*指数*小于*零*或大于 *s* 中的最后一个位置。

**注:**控制字符为格式化等非打印字符，如`ACK, BEL, CR, FF, LF, and VT`。

以下程序说明了**字符的使用。IsControl(字符串，Int32)** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Char.IsControl(String, Int32) 
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);
            check("a" + Environment.NewLine + "b", 1);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {

        // checking condition
        // using GetNumericValue() Method
        bool val = Char.IsControl(s, i);

        // checking
        if (val)
            Console.WriteLine("Control character \\U{0} "+
                                 "found in position {1}.", 
                 Convert.ToInt32(s[i]).ToString("X4"), i);

        else
            Console.WriteLine("String '{0}' does't contain control "+
                                      "character at index {1}", s, i);
    }
}
```

**Output:**

```cs
String '1234' does't contain control character at index 3
String 'Tsunami' does't contain control character at index 3
String 'psyc0lo' does't contain control character at index 4
Control character \U000A found in position 1.

```

**示例 2:** 适用于**参数异常**

```cs
// C# program to demonstrate the
// Char.IsControl(String, Int32) 
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling check() Method
            check("1234", 3);
            check("psyc0lo", 4);
            check("a" + Environment.NewLine + "b", 1);
            Console.WriteLine("");
            Console.WriteLine("s is null");
            check(null, 4);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using GetNumericValue() Method
        bool val = Char.IsControl(s, i);

        // checking
        if (val)
            Console.WriteLine("Control character \\U{0} found"+
                                           " in position {1}.",
                       Convert.ToInt32(s[i]).ToString("X4"), i);
        else
            Console.WriteLine("String '{0}' does't contain "+
                     "control character at index {1}", s, i);
    }
}
```

**Output:**

```cs
String '1234' does't contain control character at index 3
String 'psyc0lo' does't contain control character at index 4
Control character \U000A found in position 1.

s is null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为**argumentout of range exception**

```cs
// C# program to demonstrate the
// Char.IsControl(String, Int32) 
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling check() Method
            check("1234", 3);
            check("psyc0lo", 4);
            check("a" + Environment.NewLine + "b", 1);

            Console.WriteLine("");
            Console.WriteLine("index is less than zero");

            check("null", -1);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using GetNumericValue() Method
        bool val = Char.IsControl(s, i);

        // checking
        if (val)
            Console.WriteLine("Control character \\U{0} found "+
                                              "in position {1}.",
                        Convert.ToInt32(s[i]).ToString("X4"), i);
        else
            Console.WriteLine("String '{0}' does't contain control"+
                                   " character at index {1}", s, i);
    }
}
```

**Output:**

```cs
String '1234' does't contain control character at index 3
String 'psyc0lo' does't contain control character at index 4
Control character \U000A found in position 1.

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . is control？view = net framework-4 . 7 . 2 # System _ Char _ IsControl _ System _ String _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.char.iscontrol?view=netframework-4.7.2# System_Char_IsControl_System_String_System_Int32_)