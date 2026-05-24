# c# 中的长关键字

> 原文:[https://www.geeksforgeeks.org/long-keyword-in-c-sharp/](https://www.geeksforgeeks.org/long-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **long** 是一个关键字，用于声明一个变量，该变量可以存储范围从 **-9，223，372，036，854，775，808** 到 **9，223，372，036，854，775，807** 的带符号整数值。是**系统的别名。Int64** 。

**语法:**

```cs
long variable_name = value;
```

**long 关键字**占用内存中 8 字节(64 位)的空间。

**示例:**

```cs
Input: num: 34638

Output: num: 34638
        Size of a long variable: 8

Input: num = -79349367648374345

Output: Type of num: System.Int64
        num: -79349367648374345
        Size of a long variable: 8

```

如果我们输入超出范围的数字，它会显示错误-

```cs
Integral constant is too large
```

**例 1:**

```cs
// C# program for long keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        long num = 34638;

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a long variable: " + sizeof(long));
    }
}
```

**输出:**

```cs
num: 34638
Size of a long variable: 8

```

**例 2:**

```cs
// C# program for long keyword
using System;
using System.Text;

namespace Test {

class GFG {

    static void Main(string[] args)
    {
        // variable declaration
        long num = -79349367648374345;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a long variable: " + sizeof(long));

        // to print minimum & maximum value of long
        Console.WriteLine("Min value of long: " + long.MinValue);
        Console.WriteLine("Max value of long: " + long.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.Int64
num: -79349367648374345
Size of a long variable: 8
Min value of long: -9223372036854775808
Max value of long: 9223372036854775807

```