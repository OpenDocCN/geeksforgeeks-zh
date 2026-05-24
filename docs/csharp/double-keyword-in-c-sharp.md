# 在 C# 中双关键字

> 原文:[https://www.geeksforgeeks.org/double-keyword-in-c-sharp/](https://www.geeksforgeeks.org/double-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。这是一个关键字，用于声明一个变量，该变量可以存储从 **5.0 x 10 <sup>-324</sup> 到 1.7 x 10 <sup>308</sup>** 范围内的浮点值。它是 System.Double 的别名。基本上，它是一个 64 位双精度浮点数，精度为 14 到 15 位。

**Double 关键字**占用内存中 8 字节(64 位)的空间。

**语法:**

```cs
double variable_name = value;
```

我们可以指定后缀 **d** 或 **D** 来表示双精度值。不使用任何后缀的浮点值也被视为双精度值。

**示例:**

```cs
Input: num: 1234.5678

Output: num: 1234.5678
        Size of a double variable: 8

Input: num = -67895.4322D

Output: Type of num: System.Double
        num: -67895.4322
        Size of a double variable: 8

```

**例 1:**

```cs
// C# program for the double keyword
using System;
using System.Text;

class geeks {

    static void Main(string[] args)
    {
        // variable declaration
        double num = 1234.5678;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a double variable: " + sizeof(double));
    }
}
```

**输出:**

```cs
num: 1234.5678
Size of a double variable: 8

```

**例 2:**

```cs
// C# program for the double keyword
using System;
using System.Text;

namespace Test {

class geeks {

    static void Main(string[] args)
    {
        // variable declaration
        double num = -67895.4322D;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a double variable: " + sizeof(double));

        // to print minimum & maximum value of double
        Console.WriteLine("Min value of double: " + double.MinValue);
        Console.WriteLine("Max value of double: " + double.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.Double
num: -67895.4322
Size of a double variable: 8
Min value of double: -1.79769313486232E+308
Max value of double: 1.79769313486232E+308

```