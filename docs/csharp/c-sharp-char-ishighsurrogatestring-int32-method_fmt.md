# C# | Char.IsHighSurrogate(String, Int32) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-ishighsurrogatestring-int32-method/](https://www.geeksforgeeks.org/c-sharp-char-ishighsurrogatestring-int32-method/)

此方法用于指示字符串中指定位置的 `Char` 对象是否为高代理。

## 语法

```cs
public static bool IsHighSurrogate (string s, int index);
```

## 参数

- **s**：类型为 `string`。
- **index**：`s` 中的字符位置。

## 返回值

如果 `s` 参数中指定字符的数值在 `U+D800` 到 `U+DBFF` 之间，则该方法返回 `true`，否则返回 `false`。

## 异常

- `ArgumentNullException`：如果 `s` 为 `null`。
- `ArgumentOutOfRangeException`：如果 `index` 不在 `s` 的有效索引范围内。

以下程序说明了 `Char.IsHighSurrogate(String, Int32)` 方法的使用：

## 例 1

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
String 'a\uD800\uDC00z' contains High Surrogate value at index 1
```

## 示例 2：适用于 `ArgumentNullException`

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

## 例 3：为 `ArgumentOutOfRangeException`

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
String 'a\uD800\uDC00z' contains High Surrogate value at index 1

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.char.ishighsurrogate?view=netframework-4.7.2#System_Char_IsHighSurrogate_System_String_System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.char.ishighsurrogate?view=netframework-4.7.2#System_Char_IsHighSurrogate_System_String_System_Int32_)