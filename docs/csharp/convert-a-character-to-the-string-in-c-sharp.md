# 将一个字符转换成 C# 中的字符串

> 原文:[https://www . geesforgeks . org/convert-a-character-to-string-in-c-sharp/](https://www.geeksforgeeks.org/convert-a-character-to-the-string-in-c-sharp/)

给定一个字符，任务是在 C# 中将字符转换为字符串。

**例:**

```cs
Input :  X = 'a'
Output : string S = "a"

Input :  X = 'A'
Output : string S = "A"

```

**方法:**想法是使用 [ToString(](https://www.geeksforgeeks.org/c-sharp-char-tostring-method/) ) 方法，参数是字符，它返回字符串将 Unicode 字符转换为字符串。

```cs
// convert the character x
// to string s
public string ToString(IFormatProvider provider);

```

## c#

```cs
// C# program to character to the string
using System;

public class GFG{

    static string getString(char x) 
    {
        // Char.ToString() is a System.Char 
        // struct method which is used 
        // to convert the value of this
        // instance to its equivalent
        // string representation
        string str = x.ToString();

        return str;
    }

    static void Main(string[] args)
    {
        char chr = 'A';
        Console.WriteLine("Type of "+ chr +" : " + chr.GetType());

        string str = getString(chr);
        Console.WriteLine("Type of "+ str +" : " + str.GetType());

    }
}
```

**输出:**

```cs
Type of A : System.Char
Type of A : System.String

```