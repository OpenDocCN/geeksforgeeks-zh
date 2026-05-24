# c# 中读取字符的不同方法

> 原文:[https://www . geesforgeks . org/different-method-to-read-a-in-character-c-sharp/](https://www.geeksforgeeks.org/different-methods-to-read-a-character-in-c-sharp/)

在 [C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 中，我们知道**控制台。Read()** 方法用于从标准输出设备中读取单个字符。此外，还有不同的方法可以用来读取单个字符。以下方法可用于此目的:

*   **控制台。ReadLine()[0]方法**
*   **控制台。ReadKey()。奇卡法**
*   **Char。锥虫()法**
*   **转换。ToChar()方法**

### **控制台。ReadLine()[0]方法**

自，**控制台。ReadLine()** 方法是用来读取一个字符串，字符串就是字符集。所以第一个字符可以使用 **0 <sup>th</sup>** 索引提取。从而 **控制台。ReadLine()[0]** 可用于读取单个/第一个字符。

**语法:**

```cs
char_variable = Console.ReadLine()[0];

```

**示例:**使用控制台读取字符。ReadLine()[0]

## C#

```cs
// C# program to Read a character
// using Console.ReadLine()[0]

using System;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        char chr;

        // use of Console.ReadLine()[0] method
        chr = Console.ReadLine()[0];

        // printing the input character
        Console.Write(chr);
    }
}
```

**控制台输入:**

```cs
Geeks

```

**输出:**

```cs
G

```

### **控制台。ReadKey()。奇卡法**

自，**控制台。ReadKey()** 方法用于获取用户按下的下一个字符或功能键。而 **键帽**用来获取当前*系统所代表的 Unicode 字符。ConsoleKeyInfo* 对象。从而 **控制台。ReadKey()。**键帽可以用来读取单个/第一个字符。基本上，它会读取一个字符或一个功能，并在控制台上显示，但无需等待回车键按下。一旦你输入一个字符，输出就会显示在控制台上。

**语法:**

```cs
char_variable = Console.ReadKey().KeyChar;

```

**示例:**使用控制台读取字符。ReadKey()。奇卡

## C#

```cs
// C# program to Input a character
// using Console.ReadKey().KeyChar

using System;
using System.IO;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        char chr;

        // use of Console.ReadKey().KeyChar method
        chr = Console.ReadKey().KeyChar;

        // printing the input character
        Console.WriteLine(chr);
    }
}
```

**控制台输入:**

```cs
G
```

**输出:**

```cs
GG
```

### **Char。锥虫()法**

**Char。方法用来读取一个字符，它也处理异常。如果任何输入值不是字符，它将抛出一个错误。它还返回输入状态，对于有效字符为真，对于无效字符为假。**

**语法:**

```cs
bool result = Char.TryParse(String s, out char char_variable);

```

**示例:**使用 Char 读取字符。锥虫()

## C#

```cs
// C# program to Read a character
// using Char.TryParse()

using System;
using System.IO;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        char chr;
        bool val;

        // use of Char.TryParse() method
        val = Char.TryParse(Console.ReadLine(), out chr);

        //printing the input character
        Console.WriteLine("Result: " + val);
        Console.WriteLine("Input character: " + chr);
    }
}
```

**控制台输入:**

```cs
G

```

**输出:**

```cs
Result: True
Input character: G

```

### **转换。ToChar()方法**

**转换。方法用于将指定字符串的值转换为字符。绳子的长度必须是 **1** 否则会出错。**

**语法:**

```cs
char_variable = Convert.ToChar(string s);

```

**示例:**使用 Convert 读取字符。ToChar()

## C#

```cs
// C# program to Read a character
// using Convert.ToChar()

using System;
using System.IO;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        char chr;

        // use of Convert.ToChar() method
        chr = Convert.ToChar(Console.ReadLine());

        // printing the input character
        Console.WriteLine(chr);
    }
}
```

**控制台输入:**

```cs
G

```

**输出:**

```cs
G

```