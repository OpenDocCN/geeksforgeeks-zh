# C# |功能委托

> 原文：[https://www.geeksforgeeks.org/c-sharp-func-delegate/](https://www.geeksforgeeks.org/c-sharp-func-delegate/)

## 先决条件：[c# 中的代表](https://www.geeksforgeeks.org/c-sharp-delegates/)

创建自定义委托时，我们必须遵循以下步骤：

**步骤 1：** 用与方法完全相同的格式声明一个自定义委托。

**步骤 2：** 创建自定义委托的对象。

**第三步：** 调用方法。

通过使用这些步骤，我们创建了如下程序所示的自定义委托。但是问题是，为了创建一个委托，我们需要遵循上面的过程。为了克服这种情况，C# 提供了一个内置的委托 `Func`。使用 `Func` 委托，您不需要遵循以下过程来创建委托。

## 示例

```cs
// C# program to illustrate how to 
// create custom delegates
using System;

class GFG {

    // Declaring the delegate
    public delegate int my_delegate(int s, int d,
                                   int f, int g);

    // Method
    public static int mymethod(int s, int d,
                              int f, int g)
    {
        return s * d * f * g;
    }

    // Main method
    static public void Main()
    {

        // Creating object of my_delegate
        my_delegate obj = mymethod;
        Console.WriteLine(obj(12, 34, 35, 34));
    }
}
```

## 输出

```cs

```

`Func` 是内置的泛型类型委托。这个委托使您不必像上面的例子那样定义一个自定义委托，并使您的程序更加易读和优化。我们知道，`Func` 是一个通用委托，所以它是在 `System` 命名空间下定义的。它可以**包含最小 0 和最大 16 个输入参数**，而**只包含一个输出参数**。`Func` 委托的最后一个参数是 out 参数，被认为是返回类型，用于结果。`Func` 通常用于那些将要返回值的方法，或者换句话说，`Func` 委托用于返回值的方法。它还可以包含相同类型或不同类型的参数。

## 语法

> //零个正常参数和一个结果参数
> public delegate TResult Func<out TResult>();
> 
> //一个正常参数和一个结果参数
> public delegate TResult Func<in T, out TResult>(T arg);
> 
> //两个正常参数和一个结果参数
> public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
> 
> //十六个正常参数和一个结果参数
> public delegate TResult Func<in T1, in T2, in T3, in T4, in T5, in T6, in T7, in T8, in T9, in T10, in T11, in T12, in T13, in T14, in T15, in T16, out TResult>(T1 arg1, T2 arg2, T3 arg3, T4 arg4, T5 arg5, T6 arg6, T7 arg7, T8 arg8, T9 arg9, T10 arg10, T11 arg11, T12 arg12, T13 arg13, T14 arg14, T15 arg15, T16 arg16);

这里，`T1`、`T2`…`T16` 为输入参数类型，`TResult` 为输出参数类型，`arg1`…`arg16` 是 `Func` 委托封装的方法的参数。

## 示例 1

这里，我们使用 `Func` 委托只在一行中创建委托，而不使用上述过程。该 `Func` 委托包含四个输入参数和一个输出参数。

```cs
// C# program to illustrate Func delegate
using System;

class GFG {

    // Method
    public static int mymethod(int s, int d, int f, int g)
    {
        return s * d * f * g;
    }

    // Main method
    static public void Main()
    {

        // Using Func delegate
        // Here, Func delegate contains
        // the four parameters of int type
        // one result parameter of int type
        Func<int, int, int, int, int> val = mymethod;
        Console.WriteLine(val(10, 100, 1000, 1));
    }
}
```

## 输出

```cs

```

## 例 2

```cs
// C# program to illustrate Func delegate
using System;

class GFG {

    // Method
    public static int method(int num)
    {
        return num + num;
    }

    // Main method
    static public void Main()
    {

        // Using Func delegate
        // Here, Func delegate contains 
        // the one parameters of int type
        // one result parameter of int type
        Func<int, int> myfun = method;
        Console.WriteLine(myfun(10));
    }
}
```

## 输出

```cs

```

## 要点

*   `Func` Delegate 中的最后一个参数始终是一个 out 参数，它被视为返回类型。它通常用于结果。
*   您也可以将 `Func` 委托与匿名方法一起使用。如下例所示：

```cs
Func<int, int, int> val = delegate(int x, int y, int z)
{
    return x + y + z;
};
```

*   您也可以将 `Func` 委托与 lambda 表达式一起使用。如下例所示：

```cs
Func<int, int, int, int> val = (int x, int y, int z) => x + y + z;
```