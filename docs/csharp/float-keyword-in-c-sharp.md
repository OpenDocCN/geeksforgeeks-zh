# c# 中的 float 关键字

> 原文:[https://www.geeksforgeeks.org/float-keyword-in-c-sharp/](https://www.geeksforgeeks.org/float-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **float** 是一个用于声明变量的关键字，该变量可以存储从 **1.5 x 10 <sup>-45</sup> 到 3.4 x 10 <sup>38</sup>** 范围内的浮点值。是**系统的别名。单**。

**语法:**

```cs
float variable_name = value;
```

**float 关键字**占用内存中 4 个字节(32 位)的空间。我们使用后缀 **f** 或 **F** 的值来表示浮点值。

**示例:**

```cs
Input: -3629.4586F

Output: num: -3629.458
        Size of a float variable: 4

Input: 16345.6456f

Output: Type of num: System.Single
        num: 16345.65
        Size of a float variable: 4
        Min value of float: -3.402823E+38
        Max value of float: 3.402823E+38

```

**例 1:**

```cs
// C# program for float keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        float num = -3629.4586F;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a float variable: " + sizeof(float));
    }
}
```

**输出:**

```cs
num: -3629.458
Size of a float variable: 4

```

**例 2:**

```cs
// C# program for float keyword
using System;
using System.Text;

namespace geeks {

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        float num = 16345.6456f;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a float variable: " + sizeof(float));

        // to print minimum & maximum value of float
        Console.WriteLine("Min value of float: " + float.MinValue);
        Console.WriteLine("Max value of float: " + float.MaxValue);
    }
}
}
```

**输出:**

```cs
Type of num: System.Single
num: 16345.65
Size of a float variable: 4
Min value of float: -3.402823E+38
Max value of float: 3.402823E+38

```