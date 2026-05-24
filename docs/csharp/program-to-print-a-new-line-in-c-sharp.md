# 用 C# 打印新行的程序

> 原文:[https://www . geesforgeks . org/program-to-print-a-new-line-in-c-sharp/](https://www.geeksforgeeks.org/program-to-print-a-new-line-in-c-sharp/)

有多种方法可以在消息中打印新行

*   使用:**\ n**–打印新行。
*   通过使用: **\x0A 或\xA** (ASCII 文字为\ n)–它会打印新行。
*   通过使用:**控制台。WriteLine()**–打印新行。

**示例:**

```cs
Input  : GeeksForGeeks
Output : Geeksfor
         Geeks

Input : Save World
Output: Save
        World

```

下面是上述方法的实现:

**例 1:**

```cs
// C# program to print a new line
using System;
using System.IO;
using System.Text;

namespace geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {
            // by using \n
            Console.WriteLine("Geeksfor\nGeeks");

            // by using \x0A
            Console.WriteLine("Geeks\x0A ForGeeks");

        }
    }
}
```

**输出:**

```cs
Geeksfor
Geeks
Geeks
 ForGeeks

```

**例 2:**

```cs
// C# program to print a new line
using System;
using System.IO;
using System.Text;

namespace geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {

            Console.WriteLine("Print a new line");

            // print only next line
            Console.WriteLine();

            // by using \n
            Console.WriteLine("Save\nWorld");

            // by using \x0A
            Console.WriteLine("Stay\x0ASafe");

            // ENTER to exit the program
            Console.ReadLine();
        }
    }
}
```

**输出:**

```cs
Print a new line

Save
World
Stay
Safe

```