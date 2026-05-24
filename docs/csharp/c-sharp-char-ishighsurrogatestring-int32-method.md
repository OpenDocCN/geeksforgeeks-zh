# C# | Char。IsHighSurrogate(字符串，Int32)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-ishighboragetestring-int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-ishighsurrogatestring-int32-method/)

此方法用于指示字符串中指定位置的 Char 对象是否为高代理。

**语法:**

```cs
public static bool IsHighSurrogate (string s, int index);
```

**参数:**

> **s** :是一根弦。
> 
> **索引**:是 *s* 中的人物位置。

**返回值:**如果 s 参数中指定字符的数值在`U+D800`到`U+DBFF;`之间，则该方法返回*真*，否则返回*假*。

**异常:**

*   **参数空异常:**如果 *s* 为空。
*   **argumentout of range exception:**如果*指数*不在*的*之内。

以下程序说明了**字符的使用。IsHighSurrogate(字符串，Int32)** 方法:

**例 1:**

```cs
// C# program to demonstrate the 
// Char.IsHighSurrogate(String, 
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
            string s1 = new String(new char[] { 'a', 
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
        // using IsHighSurrogate() Method
        bool val = Char.IsHighSurrogate(s, i);

        // checking
        if (val)

            Console.WriteLine("String '{0}' contains High "
                  + "Surrogate value at index {1} ", s, i);
        else
          Console.WriteLine("String '{0}' does't contain any High"
                          + "Surrogate value at index {1}", s, i);

    }
}
```

**Output:**

```cs
String '1234' does't contain any HighSurrogate value at index 3
String 'Tsunami' does't contain any HighSurrogate value at index 3
String 'psyc0lo' does't contain any HighSurrogate value at index 4
String 'að??z' contains High Surrogate value at index 1

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the 
// Char.IsHighSurrogate(String, 
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
            Console.WriteLine("");
            Console.WriteLine("s is null");
            check(null, 4);

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
        // using IsHighSurrogate() Method
        bool val = Char.IsHighSurrogate(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains High "
                   + "Surrogate value at index {1} ",s, i);

        else
            Console.WriteLine("String '{0}' does't contain any High"
                             + "Surrogate value at index {1}",s, i);

    }
}
```

**Output:**

```cs
String '1234' does't contain any HighSurrogate value at index 3
String 'Tsunami' does't contain any HighSurrogate value at index 3
String 'psyc0lo' does't contain any HighSurrogate value at index 4

s is null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the 
// Char.IsHighSurrogate(String, 
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

            // declaring and initializing string s1
            string s1 = new String(new char[] { 'a',
                         '\uD800', '\uDC00', 'z' });
            check(s1, 1);

            Console.WriteLine("");
            Console.WriteLine("index is less than zero");
            check("fjsjsj", -1);
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
        // using IsHighSurrogate() Method
        bool val = Char.IsHighSurrogate(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains High "
                  + "Surrogate value at index {1} ", s, i);

        else
            Console.WriteLine("String '{0}' does't contain any High"
                            + "Surrogate value at index {1}", s, i);

    }
}
```

**Output:**

```cs
String '1234' does't contain any HighSurrogate value at index 3
String 'Tsunami' does't contain any HighSurrogate value at index 3
String 'að??z' contains High Surrogate value at index 1 

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . ishigh surrogate？view = net framework-4 . 7 . 2 # System _ Char _ ishightsurrogate _ System _ String _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.char.ishighsurrogate?view=netframework-4.7.2# System_Char_IsHighSurrogate_System_String_System_Int32_)