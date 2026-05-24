# c# 中的 var 关键字

> 原文:[https://www.geeksforgeeks.org/var-keyword-in-c-sharp/](https://www.geeksforgeeks.org/var-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **var** 是一个关键字，它用来声明一个隐式类型变量，即基于**初始值**指定一个变量的类型。

**语法:**

```cs
var variable_name = value;
```

**示例:**

```cs
Input: a = 637
       b = -9721087085262

Output: value of a 637, type System.Int32
        value of b -9721087085262, type System.Int64

Input: c = 120.23f
       d = 150.23m
       e = G
       f = Geeks
Output: value of c 120.23, type System.Single
        value of d 150.23, type System.Decimal
        value of e G, type System.Char
        value of f Geeks, type System.String

```

**例 1:**

```cs
// C# program for var keyword
using System;
using System.Text;

class GFG {

    static void Main(string[] args)
    {

        var a = 637;
        var b = -9721087085262;

        // to print their type of variables
        Console.WriteLine("value of a {0}, type {1}", a, a.GetType());
        Console.WriteLine("value of b {0}, type {1}", b, b.GetType());
    }
}
```

**输出:**

```cs
value of a 637, type System.Int32
value of b -9721087085262, type System.Int64

```

**例 2:**

```cs
// C# program for var keyword
using System;
using System.Text;

namespace Test {

class GFG {

    static void Main(string[] args)
    {

        var c = 120.23f;
        var d = 150.23m;
        var e = 'G';
        var f = "Geeks";

        // to print their type of variables
        Console.WriteLine("value of c {0}, type {1}", c, c.GetType());
        Console.WriteLine("value of d {0}, type {1}", d, d.GetType());
        Console.WriteLine("value of e {0}, type {1}", e, e.GetType());
        Console.WriteLine("value of f {0}, type {1}", f, f.GetType());

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
value of c 120.23, type System.Single
value of d 150.23, type System.Decimal
value of e G, type System.Char
value of f Geeks, type System.String

```