# C# |如何将一个字符串复制到另一个字符串中

> 原文:[https://www . geesforgeks . org/c-sharp-如何将一个字符串复制到另一个字符串中/](https://www.geeksforgeeks.org/c-sharp-how-to-copy-a-string-into-another-string/)

**弦。复制(字符串)方法**用于创建与指定的[字符串](https://www.geeksforgeeks.org/c-string-class/)具有相同值的字符串的新实例。换句话说，这种方法用于将一个字符串的数据复制到一个新的[字符串](https://www.geeksforgeeks.org/c-string-class/)中。
新字符串包含与原始字符串相同的数据，但表示不同的对象引用。

**语法:**

```cs
public static string Copy (string value);
```

**参数:**此处*值*是要复制的字符串。

**返回值:**该方法的返回类型为**系统。弦**。该方法返回一个新字符串，该字符串包含类似于*值*的数据。

**异常:**如果*值*为空，该方法将给出 ArgumentNullException。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# program to illustrate Copy() Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // string which is to be copied
        string strA = "GeeksforGeeks";

        // Copy the data of strA string
        // into strB string
        // using Copy() method
        string strB = String.Copy(strA);

        Console.WriteLine("Original String strA: {0}", strA);
        Console.WriteLine("Copied String strB: {0}", strB);
    }
}
```

**Output:**

```cs
Original String strA: GeeksforGeeks
Copied String strB: GeeksforGeeks

```

**例 2:**

```cs
// C# program to check reference of strings
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // string
        string strA = "GeeksforGeeks";
        string strB = "C# Tutorials";
        Console.WriteLine("Original string A: {0}", strA);
        Console.WriteLine("Original string B: {0}", strB);
        Console.WriteLine();

        Console.WriteLine("After copy:");

        // copy the data of strA string 
        // into strB string
        // using Copy() method
        strB = String.Copy(strA);

        Console.WriteLine("Value of string A: {0}", strA);
        Console.WriteLine("Value of string B: {0}", strB);

        // Checking the reference of both string
        Console.WriteLine("Is reference of strings is equal : {0}",
                               Object.ReferenceEquals(strA, strB));
    }
}
```

**Output:**

```cs
Original string A: GeeksforGeeks
Original string B: C# Tutorials

After copy:
Value of string A: GeeksforGeeks
Value of string B: GeeksforGeeks
Is reference of strings is equal : False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . string . copy？视图= net framework-4 . 7 . 2 # 定义](https://docs.microsoft.com/en-us/dotnet/api/system.string.copy?view=netframework-4.7.2# definition)