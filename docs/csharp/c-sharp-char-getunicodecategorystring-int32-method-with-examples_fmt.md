# C# | Char.GetUnicodeCategory(String, Int32)方法示例

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-getunicodecategorystring-int32-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-char-getunicodecategorystring-int32-method-with-examples/)

此方法用于将指定字符串中指定位置的字符分类到由其中一个 `UnicodeCategory` 值标识的组中。

## 语法

> `public static UnicodeCategory GetUnicodeCategory(string s, int index);`

## 参数

*   `s`：是字符串。
*   `index`：是 `s` 中的字符位置。

## 返回值

该方法返回一个 `UnicodeCategory` 枚举常量，该常量标识包含位于 `s` 中位置 `index` 处的字符的组。

## 异常

*   `ArgumentNullException`：如果 `s` 为 `null`。
*   `ArgumentOutOfRangeException`：如果 `index` 小于零或者大于 `s` 中的最后一个位置。

以下程序说明了 `Char.GetUnicodeCategory(String, Int32)` 方法的使用：

## 例 1

```cs
// C# program to demonstrate the
// Char.GetUnicodeCategory(String,
// Int32) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 0);
            check("psyc0lo", 2);
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
        UnicodeCategory val = Char.GetUnicodeCategory(s, i);

// Display the values
        Console.WriteLine("the letter present at "+
                      "index {0} is {1} ", i, val);
    }
}
```

**Output:**

```cs
the letter present at index 3 is DecimalDigitNumber 
the letter present at index 0 is UppercaseLetter 
the letter present at index 2 is LowercaseLetter
```

## 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Char.GetUnicodeCategory(String,
// Int32) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 0);
            check("psyc0lo", 2);
            Console.WriteLine("");
            Console.WriteLine("s is null");
            check(null, 2);
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
        UnicodeCategory val = Char.GetUnicodeCategory(s, i);

// Display the values
        Console.WriteLine("the letter present at "+
                      "index {0} is {1} ", i, val);
    }
}
```

**Output:**

```cs
the letter present at index 3 is DecimalDigitNumber 
the letter present at index 0 is UppercaseLetter 
the letter present at index 2 is LowercaseLetter

s is null
Exception Thrown: System.ArgumentNullException
```

## 例 3：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// Char.GetUnicodeCategory(String,
// Int32) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// calling check() Method
            check("1234", 3);
            check("Tsunami", 0);
            check("psyc0lo", 2);
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
        UnicodeCategory val = Char.GetUnicodeCategory(s, i);

// Display the values
        Console.WriteLine("the letter present at "+
                      "index {0} is {1} ", i, val);
    }
}
```

**Output:**

```cs
the letter present at index 3 is DecimalDigitNumber 
the letter present at index 0 is UppercaseLetter 
the letter present at index 2 is LowercaseLetter

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.char.getunicodecategory?view=netframework-4.7.2#System_Char_GetUnicodeCategory_System_String_System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.char.getunicodecategory?view=netframework-4.7.2#System_Char_GetUnicodeCategory_System_String_System_Int32_)