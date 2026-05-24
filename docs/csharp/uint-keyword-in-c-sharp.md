# c# 中的 uint 关键字

> 原文:[https://www.geeksforgeeks.org/uint-keyword-in-c-sharp/](https://www.geeksforgeeks.org/uint-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **uint** 是一个关键字，用于声明一个变量，该变量可以存储从 **0** 到 **4，294，967，295** 范围内的整数值类型(无符号整数)。It 关键字是**系统的别名。UInt32** 。

**uint 关键字**占用内存中 4 个字节(32 位)的空间。

**语法:**

```cs
uint variable_name = value;
```

**示例:**

```cs
Input: num: 67

Output: num2: 67
        Size of a uint variable: 4

Input: num = 24680

Output: Type of num1: System.UInt32
        num1: 24680
        Size of a uint variable: 4

```

**例 1:**

```cs
// C# program for uint keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        uint num2 = 67;

        // to print value
        Console.WriteLine("num2: " + num2);

        // to print size
        Console.WriteLine("Size of a uint variable: " + sizeof(uint));
    }
}
```

**输出:**

```cs
num2: 67
Size of a uint variable: 4

```

**例 2:**

```cs
// C# program for uint keyword
using System;
using System.Text;

namespace Geeks {

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        uint num1 = 24680;

        // to print type of variable
        Console.WriteLine("Type of num1: " + num1.GetType());

        // to print value
        Console.WriteLine("num1: " + num1);

        // to print size
        Console.WriteLine("Size of a uint variable: " + sizeof(uint));

        // to print minimum & maximum value of uint
        Console.WriteLine("Min value of uint: " + uint.MinValue);
        Console.WriteLine("Max value of uint: " + uint.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num1: System.UInt32
num1: 24680
Size of a uint variable: 4
Min value of uint: 0
Max value of uint: 4294967295

```

**例 3:**

```cs
// C# program for uint keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        uint num2 = 4294967297;

        // to print type of variable
        Console.WriteLine("Type of num2: " + num2.GetType());

        // to print value
        Console.WriteLine("num2: " + num2);

        // to print size
        Console.WriteLine("Size of a uint variable: " + sizeof(uint));
    }
}
```

**错误:**当我们输入了错误的整数，同时输入了超出范围的数字

> 常量值“4294967297”不能转换为“uint”