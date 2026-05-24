# 嵌套条件运算符的 C# 程序

> 原文:[https://www . geesforgeks . org/c-program-for-nested-conditional-operator/](https://www.geeksforgeeks.org/c-program-for-nested-conditional-operator/)

内部条件运算符可以用在任何块中，它显示像(a>b)？((a>c)？甲:丙:乙:丙？乙:丙)。在这里，我们输入三个数字，并使用嵌套条件运算符找到最大的数字。

**语法:**

```cs
(logical_test1) ? 
        ((logical_test2)? True_block : false_block) : 
        false_block_outer;

```

通过上面的条件操作符，它逐个检查条件是否为真，然后执行“真 _ 块”，否则执行“假 _ 块”，如果第一个为假，则执行“假 _ 块 _ 外部”。

**示例:**

```cs
Input: Enter first number : 23
       Enter second number: 45
       Enter third number : 87

// check by using this method 
// (a>b)?((a>c)?a:c):(b>c?b:c);
Output: Largest number is 87

```

**例 1:**

## C#

```cs
// C# program to illustrate example of
// nested conditional operator
using System;
using System.IO;
using System.Text;

namespace Geeks {
class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // to find largest of three  numbers
        int a;
        int b;
        int c;

        // to input numbers
        Console.Write("Enter first number : ");
        a = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter second number: ");
        b = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter third number : ");
        c = Convert.ToInt32(Console.ReadLine());

        // to find largest number
        int large = (a > b) ? ((a > c) ? a : c) : (b > c ? b : c);

        Console.WriteLine("Largest number is {0}", large);

        // hit ENTER to exit the program
        Console.ReadLine();
    }
}
}
```

**输入:**

```cs
Enter first number : 23
Enter second number: 45
Enter third number : 87
```

**输出:**

```cs
Enter first number : 23
Enter second number: 45
Enter third number : 87
Largest number is 87

```

**例 2:**

## C#

```cs
// C# program to illustrate example of
// nested conditional operator
using System;
using System.IO;

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // to find largest of three  numbers
        int a;
        int b;
        int c;

        // to input numbers
        Console.Write("Enter first number : ");
        a = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter second number: ");
        b = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter third number : ");
        c = Convert.ToInt32(Console.ReadLine());

        // to find largest number
        int large = (a > b) ? ((a > c) ? a : c) : (b > c ? b : c);

        Console.WriteLine("Largest number is {0}", large);
    }
}
```

**输入:**

```cs
Enter first number : 365
Enter second number: 123
Enter third number : 638
```

**输出:**

```cs
Enter first number : 365
Enter second number: 123
Enter third number : 638
Largest number is 638

```