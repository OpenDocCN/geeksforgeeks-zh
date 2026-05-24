# c# 中的 bool 关键字

> 原文:[https://www.geeksforgeeks.org/bool-keyword-in-c-sharp/](https://www.geeksforgeeks.org/bool-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **bool** 是一个关键字，用于声明一个可以存储布尔值 true 或 false 的变量。是**系统的别名。布尔**。

**Bool 关键字**占用内存 1 字节(8 位)。bool 只有两种可能的值，即*真*或*假*。

**语法:**

```cs
bool variable_name = value;
```

**示例:**

```cs
Input: true

Output: answer: False
        Size of a byte variable: 1

Input: false

Output: Type of answer: System.Boolean
        answer: True
        Size of a bool variable: 1

```

**例 1:**

```cs
// C# program for bool keyword
using System;
using System.Text;

    class GFG
    {
        static void Main(string[] args)
        { 
            // bool variable declaration
            bool answer = false;

            // to print value
            Console.WriteLine("answer: " + answer);

            // to print size of a bool 
            Console.WriteLine("Size of a bool variable: " + sizeof(bool));

        }
    }
```

**输出:**

```cs
answer: False
Size of a bool variable: 1

```

**例 2:**

```cs
// C# program for bool keyword
using System;
using System.Text;

namespace geeks {

class GFG {

    static void Main(string[] args)
    {
        // bool variable declaration
        bool answer = true;

        // to print type of variable
        Console.WriteLine("Type of answer: " + answer.GetType());

        // to print value
        Console.WriteLine("answer: " + answer);

        // to print size of a bool
        Console.WriteLine("Size of a bool variable: " + sizeof(bool));

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of answer: System.Boolean
answer: True
Size of a bool variable: 1

```