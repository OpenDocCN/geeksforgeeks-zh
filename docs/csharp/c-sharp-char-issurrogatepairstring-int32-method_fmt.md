# C# | Char.IsSurrogatePair(String, Int32) 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-char-issurrogatepairstring-int32-method/](https://www.geeksforgeeks.org/c-sharp-char-issurrogatepairstring-int32-method/)

此方法用于指示字符串中指定位置的两个相邻字符对象是否形成代理项对。

## 语法

```cs
public static bool IsSurrogatePair (string s, int index);
```

## 参数

- `s`：是一个字符串。
- `index`：是在 `s` 内评价的一对人物的起始位置。

## 返回值

如果 `s` 参数包含位置 `index` 和 `index + 1` 处的相邻字符，并且位置 `index` 处字符的数值范围为 `U+D800` 到 `U+DBFF`，位置 `index + 1` 处字符的数值范围为 `U+DC00` 到 `U+DFFF`，则该方法返回 `true`。

## 异常

- `ArgumentNullException`：如果 `s` 为 `null`。
- `ArgumentOutOfRangeException`：如果 `index` 不在 `s` 的范围内。

以下程序说明了 `Char.IsSurrogatePair(String, Int32)` 方法的使用：

## 例 1

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

## 示例 2：适用于 `ArgumentNullException`

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

## 例 3：为 `ArgumentOutOfRangeException`

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

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.char.issurrogatepair?view=netframework-4.7.2#System_Char_IsSurrogatePair_System_String_System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.char.issurrogatepair?view=netframework-4.7.2#System_Char_IsSurrogatePair_System_String_System_Int32_)