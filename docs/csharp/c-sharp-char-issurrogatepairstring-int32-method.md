# C# | Char。问题配对(字符串，Int32)方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-issurrogatepairstring-int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-issurrogatepairstring-int32-method/)

此方法用于指示字符串中指定位置的两个相邻字符对象是否形成代理项对。

**语法:**

```cs
public static bool IsSurrogatePair (string s, int index);
```

**参数:**

> **s** :是一根弦。
> 
> **索引**:是在 *s* 内评价的一对人物的起始位置。

**返回值:**如果 *s* 参数包含位置*索引*和*索引+ 1* 处的相邻字符，并且位置索引处字符的数值范围为`U+D800` 到`U+DBFF`，位置*索引+ 1* 处字符的数值范围为`U+DC00`到`U+DFFF`，则该方法返回 *false* 。

**异常:**

*   **参数空异常:**如果 *s* 为空。
*   **argumentout of range exception:**如果*指数*不在*的*之内。

以下程序说明了**字符的使用。IsSurrogatePair(字符串，Int32)方法:**

**例 1:**

```cs
// C# program to demonstrate the
// Char.IsSurrogatePair(String, 
// Int32) Method
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

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });

            check(s1, 1);
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
        // using IsSurrogatePair() Method
        bool val = Char.IsSurrogatePair(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains "
              + "Surrogate pairs at s[{1}] and s[{2}]",
                                          s, i, i + 1);

        else
            Console.WriteLine("String '{0}' does't contain any "
                       + "Surrogate pairs at s[{1}] and s[{2}]",
                                                    s, i, i + 1);

    }
}
```

**Output:**

```cs
String '1234' does't contain any Surrogate pairs at s[3] and s[4]
String 'Tsunami' does't contain any Surrogate pairs at s[3] and s[4]
String 'psyc0lo' does't contain any Surrogate pairs at s[4] and s[5]
String 'að??z' contains Surrogate pairs at s[1] and s[2]

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// Char.IsSurrogatePair(String, 
// Int32) Method
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

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });

            check(s1, 1);

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
        // using IsSurrogatePair() Method
        bool val = Char.IsSurrogatePair(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains "
              + "Surrogate pairs at s[{1}] and s[{2}]",
                                          s, i, i + 1);
        else
            Console.WriteLine("String '{0}' does't contain any "
                       + "Surrogate pairs at s[{1}] and s[{2}]",
                                                   s, i, i + 1);
    }
}
```

**Output:**

```cs
String '1234' does't contain any Surrogate pairs at s[3] and s[4]
String 'Tsunami' does't contain any Surrogate pairs at s[3] and s[4]
String 'psyc0lo' does't contain any Surrogate pairs at s[4] and s[5]
String 'að??z' contains Surrogate pairs at s[1] and s[2]

s is null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// Char.IsSurrogatePair(String, 
// Int32) Method
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

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });

            check(s1, 1);

            Console.WriteLine("");
            Console.WriteLine("index is less than zero");
            check("null", -4);
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
        // using IsSurrogatePair() Method
        bool val = Char.IsSurrogatePair(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains "
              + "Surrogate pairs at s[{1}] and s[{2}]",
                                          s, i, i + 1);
        else
            Console.WriteLine("String '{0}' does not contain any "
                        + "Surrogate pairs at s[{1}] and s[{2}]",
                                                    s, i, i + 1);
    }
}
```

**Output:**

```cs
String '1234' does not contain any Surrogate pairs at s[3] and s[4]
String 'Tsunami' does not contain any Surrogate pairs at s[3] and s[4]
String 'psyc0lo' does not contain any Surrogate pairs at s[4] and s[5]
String 'að??z' contains Surrogate pairs at s[1] and s[2]

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . issurrogatepair？view = net framework-4 . 7 . 2 # System _ Char _ IsSurrogatePair _ System _ String _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.char.issurrogatepair?view=netframework-4.7.2# System_Char_IsSurrogatePair_System_String_System_Int32_)