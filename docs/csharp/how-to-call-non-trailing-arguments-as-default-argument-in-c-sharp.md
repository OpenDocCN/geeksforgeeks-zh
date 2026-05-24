# 如何在 C# 中调用非尾随参数作为默认参数？

> 原文:[https://www . geeksforgeeks . org/如何调用非尾随参数作为默认参数-in-c-sharp/](https://www.geeksforgeeks.org/how-to-call-non-trailing-arguments-as-default-argument-in-c-sharp/)

C# 为函数提供了一个很好的特性，那就是函数参数可以有默认值。在没有参数的情况下调用函数时，参数会获得默认值。或者换句话说，默认参数是在方法声明中提供的值，如果在函数调用期间没有提供参数的值，则该参数将被赋予默认值。默认值是使用赋值(=)操作符赋值的，如“keywordname = value”。

*   默认参数的默认值是常量表达式。
*   每个默认参数都有一个默认值，这是其定义的一部分。
*   默认参数总是在方法中参数列表的末尾定义。当我们使用最后一个参数以外的默认参数时，编译器会给出一个错误。
*   它也被称为选项参数。

**语法:**

```cs
public void methodName(arg1, arg2, arg3 = default_Value, arg4 = default_Value)
```

**调用非尾随参数和默认参数**

当我们将非尾随参数称为默认参数时，它通常不会像预期的那样工作。通过下面的例子可以更好地理解。

> 静态 void defArgs(int a，int b = 1，int c = 2)
> 
> {
> 
> //打印值
> 
> 控制台。write line(" a =+a+"的值，"+" b =+的值"
> 
> b + "、"+"值的 c = "+c "；
> 
> }
> 
> //我们希望将 b 值赋为默认值，并将 a、c 作为参数传递给 defArg 方法
> 
> defArgs(100，200)；

这里，我们想给 a 分配 100，给 c 分配 200，给 b 留默认值，但实际发生的情况是，给 a 分配 100，给 b 分配 200，给 c 留默认值。在调用 defArg()方法时，我们可以通过对 b 后面的参数使用 parameter_name 和冒号来调用 b(即非尾随参数)作为默认参数

**进场:**

> *   创建一个方法，例如 defArgs()。在方法定义中，取 3 个参数，第 2 个和第 3 个参数使用赋值运算符(=)赋值。
> 
> ```cs
> static void defArgs(int a, int b = 1, int c = 2, int d = 3){}
> ```
> 
> *   现在，从主方法调用 defArg()方法的非尾随参数作为默认参数。例如 defArg(100，200)，这里我们想给 a 赋值 100，给 c 赋值 200，给 b 赋值默认值。
> 
> ```cs
> defArgs(100, c:200); 
> ```
> 
> 这里 100 分配给 a，200 分配给 c 和 b，保留默认值。
> 
> *   在 defArg()方法中，使用控制台打印参数的值。WriteLine()方法。

## C#

```cs
// C# program to call non-trailing arguments 
// as default argument in C#
using System;

class GFG{

// Driver code    
public static void Main()
{

    // Calling b, d as default arguments.
    defArgs(100, c: 200);

    // Calling b as default argument.
    defArgs(100, c: 200, d: 300);
}

// Method with default arguments
// taking default value of b as 1, 
// and default value of c as 2 and d as 3.
static void defArgs(int a, int b = 1, int c = 2, int d = 3)
{

    // Printing the values
    Console.WriteLine("value of a = " + a + ",\t" +
                      "value of b = " + b + ",\t" +
                      "value of c = " + c + ",\t" +
                      "value of d = " + d);
}
}
```

**Output**

```cs
value of a = 100,    value of b = 1,    value of c = 200,    value of d = 3
value of a = 100,    value of b = 1,    value of c = 200,    value of d = 300
```