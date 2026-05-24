# c# 中的十进制关键字

> 原文:[https://www.geeksforgeeks.org/decimal-keyword-in-c-sharp/](https://www.geeksforgeeks.org/decimal-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。

**[decimal](https://www.geeksforgeeks.org/c-sharp-data-types/# :~:text=Decimal%20Types%20%3A%20The%20decimal%20type,decimal%20x%20%3D%20300.5m%3B.)** 是一个关键字，用于声明一个变量，该变量可以存储 1.0×10<sup>-28</sup>到 7.9228×10<sup>28</sup>范围内的浮动类型值。是**系统的别名。十进制**在内存中占据 16 个字节(128 位)。

**语法:**

```cs
decimal variable_name = value;
```

我们必须用**‘M’**或**‘M’**作为带字面的后缀，来表示一个十进制值。

**示例:**

```cs
Input: 7271.6521M

Output: num: 7271.6521
        Size of a decimal variable: 16

Input: -371.83436

Output: Type of num: System.Decimal
        num: -371.83436
        Size of a decimal variable: 16

```

**例 1:**

```cs
// C# program for decimal keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        decimal num1 = 7271.6521M;

        // to print value
        Console.WriteLine("num: " + num1);

        // to print size of a decimal
        Console.WriteLine("Size of a decimal variable: " + sizeof(decimal));
    }
}
```

**输出:**

```cs
num: 7271.6521
Size of a decimal variable: 16

```

**例 2:**

```cs
// C# program for decimal keyword
using System;
using System.Text;

namespace geeks {
class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        decimal num1 = -371.83436m;

        // to print type of variable
        Console.WriteLine("Type of num: " + num1.GetType());

        // to print value
        Console.WriteLine("num: " + num1);

        // to print size of a decimal
        Console.WriteLine("Size of a decimal variable: " + sizeof(decimal));

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.Decimal
num: -371.83436
Size of a decimal variable: 16

```