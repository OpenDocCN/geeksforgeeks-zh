# 将八进制字符串转换为整数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-convert-the-octal-string-to-integer-number/](https://www.geeksforgeeks.org/c-sharp-program-to-convert-the-octal-string-to-an-integer-number/)

给定一个八进制数作为输入，我们需要编写一个程序将给定的八进制数转换成等价的整数。要将八进制字符串转换为整数，我们必须使用 **Convert。函数来转换这些值。**

**示例:**

```cs
Input : 202
Output : 130

Input : 660
Output : 432

```

通过使用 foreach 循环，使用**基值 8** 将项目转换为整数。

**程序 1:**

```cs
// C# program to convert an array 
// of octal strings to integers
using System;
using System.Text;

class Prog {

    static void Main(string[] args)
    {
        string[] str = { "121", "202", "003" };
        int num1 = 0;
        try {

            // using foreach loop to access each items
            // and converting to integer numbers
            foreach(string item in str)
            {
                num1 = Convert.ToInt32(item, 8);
                Console.WriteLine(num1);
            }
        }
        catch (Exception ex) {
            Console.WriteLine(ex.ToString());
        }
    }
}
```

**输出:**

```cs
81
130
3

```

**程序 2:**

```cs
// C# program to convert an array 
// of octal strings to integers
using System;
using System.Text;

namespace geeks {

class Prog {

    static void Main(string[] args)
    {
        string[] str = { "111", "543", "333", "607", "700" };
        int num2 = 0;
        try {

            // using foreach loop to access each items
            // and converting to integer numbers
            foreach(string item in str)
            {
                num2 = Convert.ToInt32(item, 8);
                Console.WriteLine(num2);
            }
        }
        catch (Exception ex) {
            Console.WriteLine(ex.ToString());
        }
    }
}
}
```

**输出:**

```cs
73
355
219
391
448

```