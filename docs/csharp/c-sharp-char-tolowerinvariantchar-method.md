# C# | Char。tolower 不变量(Char)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-tolowerinviantachar-method/](https://www.geeksforgeeks.org/c-sharp-char-tolowerinvariantchar-method/)

此方法用于使用不变区域性的大小写规则将 Unicode 字符的值转换为其小写等效字符。

**语法:**

```cs
public static char ToLowerInvariant (char c);
```

这里， *c* 是要转换的 Unicode 字符。

**返回值:**如果 *c* 已经是小写或者不是字母，这个方法返回 *c* 参数的小写等价物，或者 *c* 的不变值。

以下程序说明了**字符的使用。**方法:

**例 1:**

```cs
// C# program to demonstrate
// Char.ToLowerInvariant()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() Method
        get('A');
        get('a');
        get('B');
        get('b');
    }

    // Defining get() method
    public static void get(char c)
    {

        // getting Unicode character
        // using ToLowerInvariant() Method
        char val = Char.ToLowerInvariant(c);

        // display the char value
        Console.WriteLine("The lowercase equivalent"+
                       " of the {0} is {1}", c, val);
    }
}
```

**Output:**

```cs
The lowercase equivalent of the A is a
The lowercase equivalent of the a is a
The lowercase equivalent of the B is b
The lowercase equivalent of the b is b

```

**例 2:**

```cs
// C# program to demonstrate
// Char.ToLowerInvariant()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing char variable
        char c = 'A';

        // getting Unicode character
        // using ToLowerInvariant() Method
        char val = Char.ToLowerInvariant(c);

        // display the char value
        Console.WriteLine("The lowercase equivalent"+
                       " of the {0} is {1}", c, val);
    }
}
```

**Output:**

```cs
The lowercase equivalent of the A is a

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . tolower involution？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.tolowerinvariant?view=netframework-4.7.2)