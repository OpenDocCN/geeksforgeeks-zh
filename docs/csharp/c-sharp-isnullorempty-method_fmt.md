# C# | IsNullOrEmpty()方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-isnullorempty-method/](https://www.geeksforgeeks.org/c-sharp-isnullorempty-method/)

在 C# 中，`IsNullOrEmpty()` 是一个字符串方法。它用于检查指定的字符串是 `null` 还是空字符串 (`""`)。如果没有赋值，字符串将为 `null`。如果一个字符串被指定为 `""` 或 `String.Empty`，它将为空。`String.Empty` 是空字符串的常量。

## 语法

```cs
public static bool IsNullOrEmpty(String str) 
```

## 说明

该方法将采用类型为 `System.String` 的参数，并且这个方法将返回一个布尔值。如果 `str` 参数为 `null` 或空字符串 (`""`)，则返回 `true`，否则返回 `false`。

## 例

```cs
Input : str  = null         // initialize by null value
        String.IsNullOrEmpty(str)
Output: True

Input : str  = String.Empty  // initialize by empty value
        String.IsNullOrEmpty(str)
Output: True 
```

## 程序

演示 `IsNullOrEmpty()` 方法的工作原理:

```cs
// C# program to illustrate 
// IsNullOrEmpty() Method
using System;
class Geeks {

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "GeeksforGeeks";
        // or declare String s2.Empty;
        string s2 = "";
        string s3 = null;

        // for String value Geeks, return true
        bool b1 = string.IsNullOrEmpty(s1);
        // For String value Empty or "", return true
        bool b2 = string.IsNullOrEmpty(s2);
        // For String value null, return true
        bool b3 = string.IsNullOrEmpty(s3);

        Console.WriteLine(b1);
        Console.WriteLine(b2);
        Console.WriteLine(b3);
    }
}
```

### 输出

```cs
False
True
True
```

## 注意

`IsNullOrEmpty` 方法可以检查一个字符串是否为 `null` 或者其值是否为空，其等效代码如下:

```cs
return s == null || s == String.Empty; 
```

## 程序

演示 `IsNullOrEmpty()` 方法的替代方案:

```cs
// C# program to illustrate the 
// similar method for IsNullOrEmpty()
using System;
class Geeks {

    // to make similar method as IsNullOrEmpty
    public static bool check(string s)
    {
        return (s == null || s == String.Empty) ? true : false;
    }

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "GeeksforGeeks";
        // or declare String s2.Empty;
        string s2 = ""; 
        string s3 = null;

        bool b1 = check(s1);
        bool b2 = check(s2);
        bool b3 = check(s3);

        // same output as above program
        Console.WriteLine(b1);
        Console.WriteLine(b2);
        Console.WriteLine(b3);
    }
}
```

### 输出

```cs
False
True
True
```

参考: [https://msdn.microsoft.com/en-us/library/system.string.isnullorempty(v=vs.110).aspx](https://msdn.microsoft.com/en-us/library/system.string.isnullorempty(v=vs.110).aspx)