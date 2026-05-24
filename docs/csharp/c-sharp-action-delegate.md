# C# |动作委托

> 原文:[https://www.geeksforgeeks.org/c-sharp-action-delegate/](https://www.geeksforgeeks.org/c-sharp-action-delegate/)

操作委托是内置的泛型类型委托。如下例所示，该委托使您不必定义自定义委托，并使您的程序更加易读和优化。在*系统*命名空间下定义。它可以包含最少 1 个和最多 16 个输入参数，并且不包含任何输出参数。操作委托通常用于那些不包含任何返回值的方法，或者换句话说，操作委托用于那些返回类型为 void 的方法。它还可以包含相同类型或不同类型的参数。

**语法:**

```cs
// One input parameter
public delegate void Action < in P > (P obj);

// Two input parameters
public delegate void Action < in P1, in P2 >(P1 arg1, P2 arg2);

```

这里，P、P1 和 P2 是输入参数的类型& arg1 和 agr2 是 Action 委托封装的方法的参数。

**示例:**下面的程序说明了我们如何创建自定义委托。

```cs
// C# program to illustrate delegates
using System;

class GFG {

    // Declaring the delegate
    public delegate void my_delegate(int p, int q);

    // Method
    public static void myfun(int p, int q)
    {
        Console.WriteLine(p - q);
    }

    // Main method
    static public void Main()
    {

        // Creating object of my_delegate
        my_delegate obj = myfun;
        obj(10, 5);
    }
}
```

**输出:**

```cs
5

```