# c# 中的 char 关键字

> 原文:[https://www.geeksforgeeks.org/char-keyword-in-c-sharp/](https://www.geeksforgeeks.org/char-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **char** 是一个关键字，用于声明一个变量，该变量存储从 **+U0000 到 U+FFFF** 范围内的字符值。是[系统的别名。Char](https://www.geeksforgeeks.org/c-sharp-char-struct/) 。

**语法:**

```cs
char variable_name = value;
```

**char 关键字**占用内存 2 字节(16 位)。

**示例:**

```cs
Input: S

Output: chr: S
        Size of a char variable: 2 

Input: G

Output: Type of chr: System.Char
        chr: G
        Size of a char variable: 2

```

**例 1:**

```cs
// C# program for char keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        char chr = 'S';

        // to print value
        Console.WriteLine("chr: " + chr);

        // to print the size of a char
        Console.WriteLine("Size of a char variable: " + sizeof(char));
    }
}
```

**输出:**

```cs
chr: S
Size of a char variable: 2

```

**例 2:**

```cs
// C# program for char keyword
using System;
using System.Text;

namespace geeks {

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        char chr = 'G';

        // to print the type of variable
        Console.WriteLine("Type of chr: " + chr.GetType());

        // to print value
        Console.WriteLine("chr: " + chr);

        // to print size of a char
        Console.WriteLine("Size of a char variable: " + sizeof(char));

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of chr: System.Char
chr: G
Size of a char variable: 2

```

**例 3:**

```cs
// C# program for char keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        char chr = 'Geeks';

        // to print value
        Console.WriteLine("chr: " + chr);

        // to print size of a char
        Console.WriteLine("Size of a char variable: " + sizeof(char));
    }
}
```

**错误:**

> 字符文字中的字符太多