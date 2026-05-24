# 将十六进制字符串转换为整数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-用于将十六进制字符串转换为整数的程序/](https://www.geeksforgeeks.org/c-program-for-converting-hexadecimal-string-to-integer/)

给定一个十六进制数作为输入，我们需要编写一个程序将给定的十六进制数转换成等价的整数。要将十六进制字符串转换为整数，我们必须使用 **Convert。函数来转换这些值。**

**语法:**

```cs
Convert.ToInt32(input_string, Input_base);

```

**这里，**

*   input_string 是包含字符串格式的十六进制数的输入。
*   input_base 是输入值的基数–对于十六进制值，它将是 16。

**示例:**

```cs
Input : 56304
Output : 353028

Input : 598f
Output : 22927

```

如果我们为例如 672g 输入了错误的值，它会显示错误:*输入一个十六进制数:System。格式异常:字符串末尾有其他不可解析的字符。*

如果我们输入大于 8 位的数字，例如 746465789，它会显示错误:*输入十六进制数:系统。OverflowException:算术运算导致溢出。*

**节目 1:**

## C#

```cs
// C# program to convert array 
// of hexadecimal strings to integers
using System;
using System.Text;

class Program {

    static void Main(string[] args)
    {
        // hexadecimal number as string
        string input = "56304";
        int output = 0;

        // converting to integer
        output = Convert.ToInt32(input, 16);

        // to print  the value
        Console.WriteLine("Integer number: " + output);
    }
}
```

**输出:**

```cs
Integer number: 353028

```

**节目 2:**

## C#

```cs
// C# program to convert array 
// of hexadecimal strings
// to integers
using System;
using System.Text;

namespace geeks {

class GFG {

    static void Main(string[] args)
    {
        string input = "";
        int output = 0;
        try {

            // input string
            Console.Write("Enter a hexadecimal number: ");
            input = Console.ReadLine();

            // converting to integer
            output = Convert.ToInt32(input, 16);

            Console.WriteLine("Integer number: " + output);
        }
        catch (Exception ex) {
            Console.WriteLine(ex.ToString());
        }

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输入:**

```cs
598f
```

**输出:**

```cs
Enter a hexadecimal number: 
Integer number: 22927

```