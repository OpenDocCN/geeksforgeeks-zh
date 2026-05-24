# c# 中的字节关键字

> 原文:[https://www.geeksforgeeks.org/byte-keyword-in-c-sharp/](https://www.geeksforgeeks.org/byte-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。**字节**是一个关键字，用于声明一个变量，该变量可以存储 0 到 255 范围内的无符号值。是**系统的别名。字节**。

**字节关键字**占用内存 1 个字节(8 位)。

**语法:**

```cs
byte variable_name = value;
```

**示例:**

```cs
Input: 250

Output: number: 250
        Size of a byte variable: 1

Input: 150

Output: Type of num1: System.Byte
        num1: 150
        Size of a byte variable: 1

```

**例 1:**

```cs
// C# program to show the usage of byte keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // byte variable declaration
        byte num = 255;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size of a byte
        Console.WriteLine("Size of a byte variable: " + sizeof(byte));
    }
}
```

**输出:**

```cs
num: 255
Size of a byte variable: 1

```

**例 2:**

```cs
// C# program to show the usage of byte keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // byte variable declaration
        byte num1 = 261;

        // to print value
        Console.WriteLine("num1: " + num1);

        // to print size of a byte
        Console.WriteLine("Size of a byte variable: " + sizeof(byte));
    }
}
```

**错误:**当我们输入的数字超出(0-255)的范围时。

```cs
Constant value `261' cannot be converted to a `byte'
```

**例 3:**

```cs
// C# program to show the usage of byte keyword
using System;
using System.Text;

namespace geeks {

class GFG {
    static void Main(string[] args)
    {
        // byte variable declaration
        byte num1 = 150;

        // to print type of variable
        Console.WriteLine("Type of num1: " + num1.GetType());

        // to print value
        Console.WriteLine("num1: " + num1);

        // to print size of a byte
        Console.WriteLine("Size of a byte variable: " + sizeof(byte));

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num1: System.Byte
num1: 150
Size of a byte variable: 1

```