# 作废 C# 中的关键字

> 原文:[https://www.geeksforgeeks.org/void-keyword-in-c-sharp/](https://www.geeksforgeeks.org/void-keyword-in-c-sharp/)

**[关键词](https://www.geeksforgeeks.org/c-sharp-keywords/)** 是一种语言中用于某种内部过程或代表某种预定义动作的词语。 **void** 是一个关键字，是数据类型的引用类型，用于指定 C# 中某个方法的返回类型。是**系统的别名。作废**。

**语法:**

```cs
public void function_name([parameters])
{
    //body of the function
}
```

*注意:*如果 C# 方法中没有参数，void 不能作为参数。

**示例:**

```cs
Input: Geeks
       multi = 50*20

Output: Geeks
        multi = 1000

Output: GeeksforGeeks
        sum = 80+20
        sub = 40-10

Output: GeeksforGeeks
        sum = 100
        sub = 30

```

**例 1:**

```cs
// C# program for void keyword
using System;
class GFG {

    public void SimpleText()
    {
        Console.WriteLine("Geeks");
    }

    public void sum(int a, int b)
    {
        Console.WriteLine("multi = " + (a * b));
    }
};

class Prog {

    static void Main(string[] args)
    {
        // calling functions
        GFG ex = new GFG();
        ex.SimpleText();
        ex.sum(50, 20);
    }
}
```

**输出:**

```cs
Geeks
multi = 1000

```

**例 2:**

```cs
// C# program for void keyword
using System;
using System.Text;

namespace Test {

class Sample {

    public void SimpleText()
    {
        Console.WriteLine("GeeksforGeeks");
    }

    public void sum(int a, int b)
    {
        Console.WriteLine("sum = " + (a + b));
    }

    public void sub(int c, int d)
    {
        Console.WriteLine("sub = " + (c - d));
    }
};

class Prog {

    static void Main(string[] args)
    {
        // calling functions
        Sample ex = new Sample();
        ex.SimpleText();
        ex.sum(80, 20);
        ex.sub(40, 10);

        // hit ENTER to exit
        Console.ReadLine();
    }
}
}
```

**输出:**

```cs
GeeksforGeeks
sum = 100
sub = 30

```