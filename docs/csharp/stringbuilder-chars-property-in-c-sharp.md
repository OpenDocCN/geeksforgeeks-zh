# StringBuilder。C# 中的字符[]属性

> 原文:[https://www . geeksforgeeks . org/stringbuilder-chars-property-in-c-sharp/](https://www.geeksforgeeks.org/stringbuilder-chars-property-in-c-sharp/)

**StringBuilder。字符[Int32]属性**用于获取或设置该实例中指定字符位置的字符。

> **语法:**public char this[int index]{ get；设置；}
> 这里的*索引*是人物的位置。
> 
> **属性值:**该属性返回位置索引处的 Unicode 字符。

**异常:**

*   **argumentoutofrangerexception:**如果在设置字符时索引超出了此实例的界限。
*   **indexout of range exception:**如果获取字符时索引超出此实例的界限。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program demonstrate
// the Chars[Int32] Property
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str = 
         new StringBuilder("GeeksforGeeks");

        // print string
        Console.WriteLine("String is "
                     + str.ToString());

        // loop through string
        // and print every Character
        for (int i = 0; i < str.Length; i++) {

            // get char at position i
            char ch = str[i];

            // print char
            Console.WriteLine("Char at position "
                              + i + " is " + ch);
        }
    }
}
```

**Output:**

```cs
String is GeeksforGeeks
Char at position 0 is G
Char at position 1 is e
Char at position 2 is e
Char at position 3 is k
Char at position 4 is s
Char at position 5 is f
Char at position 6 is o
Char at position 7 is r
Char at position 8 is G
Char at position 9 is e
Char at position 10 is e
Char at position 11 is k
Char at position 12 is s

```

**例 2:**

```cs
// C# program demonstrate
// the Chars[Int32] Property
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // add the String to StringBuilder Object
        str.Append("Geek");

        // get char at position 1
        char ch = str[1];

        // print the result
        Console.WriteLine("StringBuilder Object"
                        + " contains = " + str);

        Console.WriteLine("Character at Position 1"
                     + " in StringBuilder = " + ch);
    }
}
```

**Output:**

```cs
StringBuilder Object contains = Geek
Character at Position 1 in StringBuilder = e

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . stringbuilder . chars？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.chars?view=netframework-4.7.2)