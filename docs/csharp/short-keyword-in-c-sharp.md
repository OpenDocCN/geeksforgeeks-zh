# c# 中的短关键字

> 原文:[https://www.geeksforgeeks.org/short-keyword-in-c-sharp/](https://www.geeksforgeeks.org/short-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **short** 是一个关键字，用于声明一个变量，该变量可以存储范围从 **-32，768** 到 **32，767** 的带符号整数值。是**系统的别名。Int16** 。

**语法:**

```cs
short variable_name = value;
```

**短关键字**占用内存 2 字节(16 位)空间。

**示例:**

```cs
Input: num: 2

Output: num: 2
        Size of a short variable: 2

Input: num = 20200

Output: num: 20200
        Type of num: System.Int16
        Size of a short variable: 2

```

**例 1:**

```cs
// C# program for short keyword
using System;
using System.Text;

class Prog {

    static void Main(string[] args)
    {
        // variable declaration
        short num = 2;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a short variable: " + sizeof(short));
    }
}
```

**输出:**

```cs
num: 2
Size of a short variable: 2

```

**例 2:**

```cs
// C# program for short keyword
using System;
using System.Text;

namespace Test {

class Prog {

    static void Main(string[] args)
    {
        // variable declaration
        short num = 20200;

        // to print value
        Console.WriteLine("num: " + num);

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print size
        Console.WriteLine("Size of a short variable: " + sizeof(short));

        // to print minimum & maximum value of short
        Console.WriteLine("Min value of short: " + short.MinValue);
        Console.WriteLine("Max value of short: " + short.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
num: 20200
Type of num: System.Int16
Size of a short variable: 2
Min value of short: -32768
Max value of short: 32767

```