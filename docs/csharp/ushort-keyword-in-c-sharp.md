# c# 中的 ushort 关键字

> 原文:[https://www.geeksforgeeks.org/ushort-keyword-in-c-sharp/](https://www.geeksforgeeks.org/ushort-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **ushort** 是一个关键字，用于声明一个变量，该变量可以存储范围从 **0** 到 **65，535** 的无符号整数值。是**系统的别名。UInt16** 。

**语法:**

```cs
ushort variable_name = value;
```

**ushort 关键字**占用内存中 2 字节(16 位)的空间。

**示例:**

```cs
Input: num: 5

Output: num: 5
        Size of a ushort variable: 2

Input: num = 8765

Output: num: 8765
        Type of num: System.UInt16
        Size of a ushort variable: 2
```

**例 1:**

```cs
// C# program for ushort keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        ushort num = 5;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a ushort variable: " + sizeof(ushort));
    }
}
```

**输出:**

```cs
num: 5
Size of a ushort variable: 2

```

**例 2:**

```cs
// C# program for ushort keyword
using System;
using System.Text;

namespace Test {

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        ushort num = 8765;

        // to print value
        Console.WriteLine("num: " + num);

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print size
        Console.WriteLine("Size of a ushort variable: " + sizeof(ushort));

        // to print minimum & maximum value of ushort
        Console.WriteLine("Min value of ushort: " + ushort.MinValue);
        Console.WriteLine("Max value of ushort: " + ushort.MaxValue);
    }
}
}
```

**输出:**

```cs
num: 8765
Type of num: System.UInt16
Size of a ushort variable: 2
Min value of ushort: 0
Max value of ushort: 65535

```