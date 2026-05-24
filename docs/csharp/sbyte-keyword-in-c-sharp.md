# c# 中的字节关键字

> 原文:[https://www.geeksforgeeks.org/sbyte-keyword-in-c-sharp/](https://www.geeksforgeeks.org/sbyte-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **SByte** 是一个关键字，用于声明一个变量，该变量可以存储-128 到+127 范围内的有符号值。是**系统的别名。SByte** 。

**SByte 关键字**占用内存 1 字节(8 位)。

**语法:**

```cs
sbyte variable_name = value;
```

**SByte 关键字**可以存储-128 到+127 范围内的值。

**示例:**

```cs
Input: -109

Output: num: -109
        Size of a sbyte variable: 1

Input: 110

Output: Type of num: System.SByte
        num: 110
        Size of a sbyte variable: 1

```

**例 1:**

```cs
// C# program for sbyte keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        sbyte num = -109;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size of a sbyte
        Console.WriteLine("Size of a sbyte variable: " + sizeof(sbyte));
    }
}
```

**输出:**

```cs
num: -109
Size of a sbyte variable: 1

```

**例 2:**

```cs
// C# program for sbyte keyword
using System;
using System.Text;

namespace geeks {

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        sbyte num = 110;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size of sbyte 
        Console.WriteLine("Size of a sbyte variable: " + sizeof(sbyte));

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.SByte
num: 110
Size of a sbyte variable: 1

```

**例 3:**

```cs
// C# program for sbyte keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // char variable declaration
        sbyte num = -189;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size of a sbyte
        Console.WriteLine("Size of a sbyte variable: " + sizeof(sbyte));
    }
}
```

**错误:**当我们输入的数字超出(-128-127)的范围时。

> 常量值`-189 '不能转换为' sbyte '