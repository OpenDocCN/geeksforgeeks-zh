# 在 C# 中定义各种类型常量的程序

> 原文:[https://www . geesforgeks . org/program-to-define-各种类型的常量-in-c-sharp/](https://www.geeksforgeeks.org/program-to-define-various-types-of-constants-in-c-sharp/)

和其他编程语言一样，各种类型的**常量**的定义和 C# 中定义的一样，我们也可以定义各种类型的常量并打印它们的值。它们在程序中的值是固定的。可以有任何类型的常量，如整数、字符常量、浮点、双精度、字符串、八进制、十六进制等。

**定义常数:**使用**常数关键字**可以定义常数。它的值一旦定义就永远不能改变。

**语法:**

```cs
const data_type constant_name = value;

```

**示例:**

```cs
Input: const int a = 15;  
Output: a: 15

```

**例 1:**

```cs
// C# program to define different types of constants 
using System;
using System.Text;

namespace Geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {
            // integer constant
            const int A = 15;  

            // float constant
            const float B = 50.83f; 

            // to print above values
            Console.WriteLine("A: {0}", A);
            Console.WriteLine("B: {0}", B);

        }
    }
}
```

**输出:**

```cs
A: 15
B: 50.83

```

**例 2:**

```cs
// C# program to define different types of constants 
using System;
using System.Text;

namespace Geeks
{
    class GFG
    {
        // Main Method 
        static void Main(string[] args)
        {
            // character constant 
            const char C = 'S';

            // double constant
            const double D = 70.23;

            // string constant
            const string E = "Geeks";   

            // to print above values
            Console.WriteLine("C: {0}", C);
            Console.WriteLine("D: {0}", D);
            Console.WriteLine("E: {0}", E);

        }
    }
}
```

**输出:**

```cs
C: S
D: 70.23
E: Geeks

```