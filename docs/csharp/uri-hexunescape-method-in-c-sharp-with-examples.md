# 乌利。C# 中的 HexUnescape()方法及示例

> 原文:[https://www . geeksforgeeks . org/uri-hexunescape-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-hexunescape-method-in-c-sharp-with-examples/)

**乌利。HexUnescape()** 方法用于将字符的指定十六进制表示转换为字符。

**语法:**

```cs
public static char HexUnescape (string pattern, ref int index);

```

**参数:**

*   **字符串**–表示十六进制字符串。
*   **ref int index**–这表示模式中字符十六进制表示开始的位置。

**返回值:**该方法返回位置索引处十六进制编码表示的字符。如果索引处的字符不是十六进制编码的，则返回索引处的字符。索引的值将递增，以指向返回字符之后的字符。

**异常:**如果索引小于 0 或大于等于字符数，该方法抛出**argumentout of range Exception**。

**例 1:**

## C#

```cs
// C# program to demonstrate the  
// Uri.HexUnescape() method  
using System;   

class GFG {  

     // Main Method  
    public static void Main()  
    {  
        // Declaring and initializing 
        string str = "%70";
        char retChar;
        int index = 0;

        // using HexUnescape() method  
        retChar = Uri.HexUnescape(str,ref index);

        Console.WriteLine("Hexadecimal character: "+retChar);
    }  
}
```

**输出:**

```cs
Hexadecimal character: p

```

**例 2:**

## C#

```cs
// C# program to demonstrate the  
// Uri.HexUnescape() method  
using System;   

class GFG {  

     // Main Method  
    public static void Main()  
    {  
        // Declaring and initializing 
        string str = Convert.ToString(123, 16);
        char retChar;
        int index =    0;

        // using HexUnescape() method  
        retChar = Uri.HexUnescape(str,ref index);

        Console.WriteLine("Hexadecimal character: "+retChar);
    }  
}
```

**输出:**

```cs
Hexadecimal character: 7

```