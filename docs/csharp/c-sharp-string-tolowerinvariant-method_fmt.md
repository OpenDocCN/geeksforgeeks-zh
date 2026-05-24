# C# 字符串 ToLowerInvariant 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-string-tolowerinvariant-method/](https://www.geeksforgeeks.org/c-sharp-string-tolowerinvariant-method/)

`字符串.ToLowerInvariant` 方法用于获取使用不变区域性的大小写规则转换为小写的字符串对象的副本。这里，“不变区域性”代表一种对区域性不敏感的区域性。

## 语法

```cs
public string ToLowerInvariant ();
```

## 返回值

该方法的返回类型为 `System.String`。此方法返回一个字符串，该字符串是当前字符串的小写等价物。

下面给出了一些例子，以便更好地理解实现：

### 例 1

```cs
// C# program to illustrate
// ToLowerInvariant() method
using System;

class GFG {

    // Main method
    static public void Main()
    {
        // variables
        string strA = "WelCome tO GeeKSfOrGeeKs";
        string strB;

        // Convert strA into lowercase
        // using ToLowerInvariant() method
        strB = strA.ToLowerInvariant();

        // Display string before ToLowerInvariant() method
        Console.WriteLine("String before ToLowerInvariant:");
        Console.WriteLine(strA);
        Console.WriteLine();

        // Display string after ToLowerInvariant() method
        Console.WriteLine("String after ToLowerInvariant:");
        Console.WriteLine(strB);
    }
}
```

**Output:**

```cs
String before ToLowerInvariant:
WelCome tO GeeKSfOrGeeKs

String after ToLowerInvariant:
welcome to geeksforgeeks
```

### 例 2

```cs
// C# program to illustrate
// ToLowerInvariant() Method
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // calling function
        Convert("GEeks");
        Convert("geeks");
        Convert("GEEKS");
    }

    static void Convert(String value)
    {
        // Display  strings
        Console.WriteLine("String 1:  {0}", value);

        // Convert sting into Lowercase
        // using ToLowerInvariant() method
        value = value.ToLowerInvariant();

        // Display the Lowercase strings
        Console.WriteLine("String 2:  {0}", value);
    }
}
```

**Output:**

```cs
String 1:  GEeks
String 2:  geeks
String 1:  geeks
String 2:  geeks
String 1:  GEEKS
String 2:  geeks
```

## 注

*   不变区域性表示不区分区域性的区域性。它与英语相关，但与特定的国家或地区无关。
*   方法不修改当前实例的值。相反，它返回一个新字符串，其中当前实例中的所有字符都转换为小写。
*   这个方法不能重载。如果你试图重载这个方法，它会给你编译时的错误。

## 参考

[https://docs.microsoft.com/en-us/dotnet/api/system.string.tolowerinvariant?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.string.tolowerinvariant?view=netframework-4.7.2)