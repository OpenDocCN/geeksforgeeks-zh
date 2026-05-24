# c# 中的 int 关键字

> 原文:[https://www.geeksforgeeks.org/int-keyword-in-c-sharp/](https://www.geeksforgeeks.org/int-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **int** 是一个关键字，用于声明一个变量，该变量可以存储从 **-2，147，483，648** 到 **2，147，483，647** 范围内的整数值类型(有符号整数)。是**系统的别名。Int32** 。

**语法:**

```cs
int variable_name = value;
```

**Int 关键字**占用内存中 4 个字节(32 位)的空间。

**示例:**

```cs
Input: num: -245

Output: num: -245
        Size of an int variable: 4

Input: num = 7923645

Output: Type of num: System.Int32
        num: 7923645
        Size of a int variable: 4

```

**例 1:**

```cs
// C# program for int keyword
using System;
using System.Text;

class geeks {

    static void Main(string[] args)
    {
        // variable declaration
        int num = -245;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a int variable: " + sizeof(int));
    }
}
```

**输出:**

```cs
num: -245
Size of a int variable: 4

```

**例 2:**

```cs
// C# program for int keyword
using System;
using System.Text;

namespace Test {

class geeks {

    static void Main(string[] args)
    {
        // variable declaration
        int num = 7923645;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a int variable: " + sizeof(int));

        // to print minimum & maximum value of int
        Console.WriteLine("Min value of int: " + int.MinValue);
        Console.WriteLine("Max value of int: " + int.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.Int32
num: 7923645
Size of a int variable: 4
Min value of int: -2147483648
Max value of int: 2147483647

```

**例 3:**

```cs
// C# program for int keyword
using System;
using System.Text;

class geeks {

    static void Main(string[] args)
    {

        // variable declaration
        int num1 = 2147483650;

        // to print value
        Console.WriteLine("num1: " + num1);

        // variable declaration
        int num = 792.53;

        // to print value
        Console.WriteLine("num: " + num);
    }
}
```

**错误:**当我们输入了错误的整数，同时输入了超出范围的数字

> 常量值' 2147483650 '不能转换为' int'
> 不能隐式地将类型' double '转换为' int '