# 将二进制字符串转换为整数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-program-to-convert-a-binary-string-to-a-integer/](https://www.geeksforgeeks.org/c-program-to-convert-a-binary-string-to-an-integer/)

给定一个二进制字符串作为输入，我们需要编写一个程序，将二进制字符串转换成等价的整数。要将二进制字符串转换为整数，我们必须使用 **Convert。函数的作用是:转换值。二进制数的基数是 2。**

**语法:**

```cs
 Convert.ToInt32(String, Base/Int32);

```

**示例:**

```cs
Input  : 1010101010101010
Output : 43690

Input : 1100011000
        111100001111
        11001100110011001100

Output : 792
         3855
         838860

```

**节目 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to convert array
// of binary string to an integer
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {
        // binary number as string
        string bin_strng = "1010101010101010";
        int number = 0;

        // converting to integer
        number = Convert.ToInt32(bin_strng, 2);

        // to print  the value
        Console.WriteLine("Number value of binary \"{0}\" is = {1}", bin_strng,
                          number);
    }
}
```

**输出:**

```cs
Number value of binary "1010101010101010" is = 43690

```

**节目 2:**

## C#

```cs
// C# program to convert array
// of binary string to an integer
using System;
using System.Text;

namespace geeks {
class GFG {

    static void Main(string[] args)
    {
        // binary number as string
        string bin_strng = "1100011000";
        int number = 0;

        // converting to integer
        number = Convert.ToInt32(bin_strng, 2);

        // to print  the value
        Console.WriteLine("Number value of binary \"{0}\" is = {1}", bin_strng,
                          number);

        bin_strng = "111100001111";

        // converting to integer
        number = Convert.ToInt32(bin_strng, 2);

        // to print  the value
        Console.WriteLine("Number value of binary \"{0}\" is = {1}", bin_strng,
                          number);

        bin_strng = "11001100110011001100";

        // converting to integer
        number = Convert.ToInt32(bin_strng, 2);

        // to print the value
        Console.WriteLine("Number value of binary \"{0}\" is = {1}", bin_strng,
                          number);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Number value of binary "1100011000" is = 792
Number value of binary "111100001111" is = 3855
Number value of binary "11001100110011001100" is = 838860

```