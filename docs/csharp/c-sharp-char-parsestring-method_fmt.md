# C# | Char.Parse(String) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-char-parsestring-method/](https://www.geeksforgeeks.org/c-sharp-char-parsestring-method/)

此方法用于将指定字符串的值转换为其等效的 Unicode 字符。

## 语法：
```cs
public static char Parse (string s);
```
这里，`s` 是包含单个字符的字符串，或者为 `null`。

## 返回值：
该方法返回一个 Unicode 字符，相当于 `s` 中的唯一字符。

## 异常：
> `ArgumentNullException`：如果 `s` 为 `null`。
> `FormatException`：如果 `s` 的长度不是 1。

以下程序说明了 `Char.Parse(String)` 方法的使用：

## 示例 1：
```cs
// C# program to demonstrate the 
// Char.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling Parse() Method
            get("1");
            get("a");
            get("@");
            get("-");
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

    // Defining get() method
    public static void get(string s)
    {

        // getting Unicode character
        // using Parse() Method
        char val = Char.Parse(s);

        // display the char value
        Console.WriteLine("Unicode character "+
               "of string {0} is {1}", s, val);
    }
}
```
**输出：**
```cs
Unicode character of string 1 is 1
Unicode character of string a is a
Unicode character of string @ is @
Unicode character of string - is -
```

## 示例 2：适用于 `ArgumentNullException`
```cs
// C# program to demonstrate the 
// Char.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling Parse() Method
            get("1");
            get("a");
            get("@");
            get("-");
            Console.WriteLine("");
            Console.WriteLine("s is null");
            get(null);
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

    // Defining get() method
    public static void get(string s)
    {

        // getting Unicode character
        // using Parse() Method
        char val = Char.Parse(s);

        // display the char value
        Console.WriteLine("Unicode character of"+
                   " string {0} is {1}", s, val);
    }
}
```
**输出：**
```cs
Unicode character of string 1 is 1
Unicode character of string a is a
Unicode character of string @ is @
Unicode character of string - is -

s is null
Exception Thrown: System.ArgumentNullException
```

## 示例 3：为 `FormatException`
```cs
// C# program to demonstrate the 
// Char.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling Parse() Method
            get("1");
            get("a");
            get("@");
            get("-");
            Console.WriteLine("");
            Console.WriteLine("The length of s is not 1.");
            get("null");
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

    // Defining get() method
    public static void get(string s)
    {

        // getting Unicode character
        // using Parse() Method
        char val = Char.Parse(s);

        // display the char value
        Console.WriteLine("Unicode character of "+
                     "string {0} is {1}", s, val);
    }
}
```
**输出：**
```cs
Unicode character of string 1 is 1
Unicode character of string a is a
Unicode character of string @ is @
Unicode character of string - is -

The length of s is not 1.
Exception Thrown: System.FormatException
```

## 参考：
*   [https://docs.microsoft.com/en-us/dotnet/api/system.char.parse?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.parse?view=netframework-4.7.2)