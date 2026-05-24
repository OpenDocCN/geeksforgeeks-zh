# C# | Char。IsSymbol()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-char-issymbol-method/](https://www.geeksforgeeks.org/c-sharp-char-issymbol-method/)

在 C# 中， ***Char。*** 是一个*系统。Char* 结构方法，用于检查 Unicode 字符是否是在 *UnicodeCategory* 下定义的有效符号，如 *MathSymbol* 、 *CurrencySymbol* 、 *ModifierSymbol* 或 *OtherSymbol* 。通过向该方法传递不同类型和数量的参数，可以重载该方法。

***   □这个符号(char)□T4【Char】。IsSymbol(String，Int32)方法**

#### 夏尔。符号(字符)方法

此方法用于检查指定的 Unicode 字符是否与 UnicodeCategory 中的任何有效符号匹配。如果匹配，则返回真，否则返回假。

**语法:**

```cs
public static bool IsSymbol(char ch);

```

**参数:**

> **ch** :需要检查有效符号的 *System.char* 类型的 unicode 字符。

**返回类型:**如果指定的 Unicode 字符是有效符号，则该方法返回真，否则返回假。这个方法的返回类型是*系统.布尔.*

**示例:**

```cs
// C# program to illustrate the
// Char.IsSymbol(Char) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking if plus sign
        // is symbol or not
        char ch1 = '+';

        result = Char.IsSymbol(ch1);
        Console.WriteLine(result);

        // checking if dollar sign
        // is symbol or not
        char ch2 = '{content}apos;;

        result = Char.IsSymbol(ch2);
        Console.WriteLine(result);

        // checking if @
        // is symbol or not
        char ch3 = '@';

        result = Char.IsSymbol(ch3);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
True
True
False

```

#### 夏尔。IsSymbol(字符串，Int32)方法

此方法用于检查指定字符串中指定位置的字符是否为有效符号。如果它是一个符合 Unicode 标准的符号，则返回真，否则返回假。

**语法:**

```cs
public static bool IsSymbol(string str, int index);

```

**参数:**

> **字符串:**是*系统的必输字符串。字符串*要检查字符的类型。
> **索引:**是指定字符串中字符的位置。该参数类型为*系统。Int32* 。

**返回类型:**如果根据 Unicode 标准，指定字符串中指定索引处的字符是有效符号，则该方法返回 True，否则返回 False。这种方法的返回类型是*系统。布尔*。

**示例:**

```cs
// C# program to illustrate the
// Char.IsSymbol(String, Int32) Method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Declaration of data type
        bool result;

        // checking for symbol in
        // a string
        string str1 = "www.GeeksforGeeks.org";
        result = Char.IsSymbol(str1, 3);
        Console.WriteLine(result);

        // checking for symbol in
        // a string
        string str2 = "geeks+";
        result = Char.IsSymbol(str2, 5);
        Console.WriteLine(result);
    }
}
```

**Output:**

```cs
False
True

```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . char . issymbol？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.issymbol?view=netframework-4.7.2)