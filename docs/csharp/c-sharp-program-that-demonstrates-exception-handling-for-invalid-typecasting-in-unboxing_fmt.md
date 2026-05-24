# C# 程序，演示在取消装箱时对无效类型转换的异常处理

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-that-demonstrates-exception-handling-for-invalid-typecasting-in-unboxing/](https://www.geeksforgeeks.org/c-sharp-program-that-demonstrates-exception-handling-for-invalid-typecasting-in-unboxing/)

## 异常处理

[异常处理](https://www.geeksforgeeks.org/exception-handling-in-c-sharp/) 用于处理程序中的错误。或者我们可以说，异常是在程序执行过程中发生的、程序代码没有预料到的事件。程序不知道发生异常时要执行的操作。在这种情况下，我们可以创建一个异常对象并调用异常处理程序代码。这个异常处理程序将程序从崩溃中拯救出来，这个过程被称为异常处理。异常处理是必要的，因为它处理不需要的事件，这样程序代码对用户来说仍然有意义。我们可以通过使用 `try` 和 `catch` block 来实现这一点。

1.  **try:** 该块识别存在任何错误的代码块。如果有任何错误，那么它将发送到 `catch` 块。它可以包含一个或多个 `catch` 块，该块是使用 `try` 关键字创建的。
2.  **catch:** 这个块用于处理 `try` 块中引发的错误。`catch` 关键字用于 `catch` 块。对于 `catch` 块，绝对应该有 `try` 块。
3.  **finally:** 这个块用于运行指定的语句集，不管是否抛出异常。它是一个可选块，通过使用 `finally` 关键字创建。

**语法:**

```cs
try
{
    //语句
}
catch
{
    //处理异常
}
finally
{
    //最终块
}
```

## 类型转换

[类型转换](https://www.geeksforgeeks.org/c-sharp-type-casting/) 可以定义为将变量从一种数据类型转换为另一种数据类型的过程。如果数据类型兼容，那么 C# 进行自动类型转换。如果不可比较，则需要显式转换它们，这称为显式类型转换。

**语法**:

```cs
(数据类型)变量/对象;
```

在这里，数据类型是我们转换的数据类型，例如，我们可以将整数类型转换为短类型。

在本文中，我们必须处理将整数类型转换为短数据类型，我们将处理这个异常。

**示例:**

```cs
Input : 50
Output : Specified cast is not valid.
```

**步骤:**

1.  声明一个名为 `number` 的整数变量。
2.  将该变量转换为对象（这称为[装箱](https://www.geeksforgeeks.org/c-sharp-boxing-unboxing/)）。
3.  在 `try` 块中将整数变量转换为短数据类型。
4.  在 `catch` 块中处理异常。

**示例:**

```cs
// C# program to illustrate how to exception handling
// for invalid TypeCasting in unBoxing
using System;
class GFG{

    static void Main()
    {

        // Declare a number
        int number = 50;

        // Set this number to the object
        object object1 = number;
        try
        {

            // Type cast this object to short
            int x = (short)object1;
            System.Console.WriteLine("Unboxing the object");
        }

        // Handle exception
        catch (System.InvalidCastException e)
        {

            // Display the error message
            System.Console.WriteLine(e.Message);
        }
    }
}
```

**输出:**

```cs
Specified cast is not valid.
```