# C# |字符串。ToUpperInvariant 方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-string-toupperinvariant-method/](https://www.geeksforgeeks.org/c-sharp-string-toupperinvariant-method/)

**弦。ToUpperInvariant 方法**用于获取使用不变区域性的大小写规则转换为大写的字符串对象的副本。这里的“不变区域性”代表一种对区域性不敏感的区域性。
**语法:**

```cs
public string ToUpperInvariant ();
```

**返回值:**该方法的返回类型为**系统。弦**。此方法将返回一个字符串，该字符串相当于当前字符串的大写形式。
下面给出一些例子，以便更好地理解实现:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// ToUpperInvariant() method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // variables
        string strA = "WelCome tO GeeKSfOrGeeKs";
        string strB;

        // Convert strA into lowercase
        // using ToLowerInvariant() method
        strB = strA.ToUpperInvariant();

        // Display string before ToUpperInvariant() method
        Console.WriteLine("String before ToUpperInvariant:");
        Console.WriteLine(strA);
        Console.WriteLine();

        // Display string after ToUpperInvariant() method
        Console.WriteLine("String after ToUpperInvariant:");
        Console.WriteLine(strB);
    }
}
```

**Output:** 

```cs
String before ToUpperInvariant:
WelCome tO GeeKSfOrGeeKs

String after ToUpperInvariant:
WELCOME TO GEEKSFORGEEKS
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// ToUpperInvariant() Method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Calling function
        Convert("GEeks");
        Convert("geeks");
        Convert("GEEKS");
    }

    static void Convert(String value)
    {

        // Display  strings
        Console.WriteLine("string 1:  {0}", value);

        // Convert sting into Uppercase
        // using ToUpperInvariant() method
        value = value.ToUpperInvariant();

        // Display the Lowercase strings
        Console.WriteLine("string 2:  {0}", value);
    }
}
```

**Output:** 

```cs
string 1:  GEeks
string 2:  GEEKS
string 1:  geeks
string 2:  GEEKS
string 1:  GEEKS
string 2:  GEEKS
```

**注:**

*   不变区域性表示不区分区域性的区域性。它与英语相关，但与特定的国家或地区无关。
*   ToUpperInvariant()方法不修改当前实例的值。相反，它返回一个新字符串，其中当前实例中的所有字符都被转换为大写。
*   这个方法不能重载如果你试图重载这个方法，它会给你编译时的错误。

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . string . toupperinvariant？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.string.toupperinvariant?view=netframework-4.7.2)