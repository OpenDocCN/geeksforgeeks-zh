# C# | Char。to pperinvariant(Char)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-char-toupperinvariantschar-method/](https://www.geeksforgeeks.org/c-sharp-char-toupperinvariantchar-method/)

此方法用于使用不变区域性的大小写规则将 Unicode 字符的值转换为其大写等效字符。

**语法:**

```cs
public static char ToUpperInvariant (char c);
```

这里， *c* 是要转换的 Unicode 字符。

**返回值:**如果 *c* 已经是大写或者不是字母，这个方法返回 *c* 参数的大写等价物，或者 *c* 的不变值。

以下程序说明了**字符的使用。**方法:

**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Char.ToUpperInvariant()
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
        get('-');
    }

    // Defining get() method
    public static void get(char c)
    {

        // getting Unicode character
        // using ToUpperInvariant() Method
        char val = Char.ToUpperInvariant(c);

        // display the char value
        Console.WriteLine("The uppercase equivalent"+
                      " of the {0} is {1}", c, val);
    }
}
```

**Output:**

```cs
The uppercase equivalent of the A is A
The uppercase equivalent of the a is A
The uppercase equivalent of the B is B
The uppercase equivalent of the b is B
The uppercase equivalent of the - is -

```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Char.ToUpperInvariant()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // declaring and initializing char variable
        char c = 'a';

        // getting Unicode character
        // using ToUpperInvariant() Method
        char val = Char.ToUpperInvariant(c);

        // display the char value
        Console.WriteLine("The Uppercase equivalent"+
                       " of the {0} is {1}", c, val);
    }
}
```

**Output:**

```cs
The Uppercase equivalent of the a is A

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . toupperinvariant？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.toupperinvariant?view=netframework-4.7.2)