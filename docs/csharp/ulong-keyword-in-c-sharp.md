# c# 中的 ulong 关键字

> 原文:[https://www.geeksforgeeks.org/ulong-keyword-in-c-sharp/](https://www.geeksforgeeks.org/ulong-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **ulong** 是用于声明变量的关键字，该变量可以存储范围从 **0** 到 **18，446，744，073，709，551，615** 的无符号整数值。是**系统的别名。UInt64** 。

**ulong 关键字**占用内存中 8 字节(64 位)的空间。

**语法:**

```cs
ulong variable_name = value;
```

**示例:**

```cs
Input: num: 223

Output: num: 223
        Size of a ulong variable: 8

Input: num = 0

Output: Type of num: System.UInt64
        num: 0
        Size of a ulong variable: 8
```

**注:**

*   如果我们输入超出范围的数字，它会显示错误-

    ```cs
    Integral constant is too large
    ```

*   如果我们为 eg-34 输入了错误的值，它会显示错误-

    ```cs
    Constant value `-34' cannot be converted to a `ulong'

    ```

**Example 1:**

```cs
// C# program for ulong keyword 
using System; 
using System.Text; 

class Prog { 

    static void Main(string[] args) 
    { 
        // variable declaration 
        ulong num = 223; 

        // to print value 
        Console.WriteLine("num: " + num); 

        // to print size 
        Console.WriteLine("Size of a ulong variable: " + sizeof(ulong)); 
    } 
} 
```

**输出:**

```cs
num: 223
Size of a ulong variable: 8

```

**例 2:**

```cs
// C# program for ulong keyword
using System;
using System.Text;

namespace Test {

class Prog {

    static void Main(string[] args)
    {
        // variable declaration
        ulong num = 0;

        // to print type of variable
        Console.WriteLine("Type of num: " + num.GetType());

        // to print value
        Console.WriteLine("num: " + num);

        // to print size
        Console.WriteLine("Size of a ulong variable: " + sizeof(ulong));

        // to print minimum & maximum value of ulong
        Console.WriteLine("Min value of ulong: " + ulong.MinValue);
        Console.WriteLine("Max value of ulong: " + ulong.MaxValue);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
Type of num: System.UInt64
num: 0
Size of a ulong variable: 8
Min value of ulong: 0
Max value of ulong: 18446744073709551615

```