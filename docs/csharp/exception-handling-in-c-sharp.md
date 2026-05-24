# c# 中的异常处理

> 原文:[https://www . geesforgeks . org/异常处理-in-c-sharp/](https://www.geeksforgeeks.org/exception-handling-in-c-sharp/)

异常被定义为在程序执行期间发生的、程序代码没有预料到的事件。程序不知道发生异常时要执行的操作。在这种情况下，我们创建一个异常对象并调用异常处理程序代码。执行异常处理程序以使程序代码不崩溃的过程称为异常处理。异常处理很重要，因为它可以优雅地处理一个不需要的事件，一个异常，这样程序代码对用户来说仍然有意义。

<figure class="table">

| 关键字 | 定义 |
| 尝试 | 用于定义试块。该块保存可能引发异常的代码。 |
| 捕捉 | 用于定义捕捉块。此块捕获由 try 块引发的异常。 |
| 最后 | 用于定义最终块。该块保存默认代码。 |
| 扔 | 用于手动引发异常。 |

</figure>

让我们举一个简单的例子来理解什么是异常:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to show how
// Exceptions occur in a program
using System;

class GFG {

    static void Main(string[] args)
    {
        // Declare an array of max index 4
        int[] arr = { 1, 2, 3, 4, 5 };

        // Display values of array elements
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine(arr[i]);
        }

        // Try to access invalid index of array
        Console.WriteLine(arr[7]);
        // An exception is thrown upon executing
        // the above line
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。IndexOutOfRangeException:索引超出了数组的界限。
> 在 GFG。主(系统。<9 fa 39 B3 B4 dec 49 EB 8 af 89 DC 70 D5 a 0618>:0
> 【错误】致命未处理异常:系统。IndexOutOfRangeException:索引超出了数组的界限。
> 在 GFG。主(系统。<9 fa 39 B3 B4 dec 49 EB 8 af 89 DC 70 D5 a 0618>:0
> 中的字符串[] args) [0x0002e]

**输出:**

```cs
1
2
3
4
5
```

在上面给出的代码中，为 5 个元素定义了名为“arr”的数组，索引为 0 到 4。当我们试图访问数组中不存在的第 7 个元素时，程序代码抛出一个异常，并显示上面的消息。可以使用*系统处理异常。C# 的*类异常。这将在下面给出的代码中描述。

### 使用尝试捕获块的异常处理

下面给出的代码展示了如何使用 try-catch 块处理异常。可能生成异常的代码被放在 try 块中。在这种情况下，对第 7 个元素的访问被放在 try 块中。当执行该语句时，会生成一个异常，该异常被 catch 块捕获。类型为 *IndexOutOfRangeException* 的对象用于向用户显示已发生异常的消息。
**语法:**

```cs
try
{
  // statements that may cause an exception
}
catch( Exception obj)
{
  // handler code
}
```

## c sharp . c sharp . c sharp . c sharp

```cs
// Exception handling of above code
// using try catch blocks

using System;

class Program : System.Exception {
    static void Main(string[] args)
    {
        // Declare an array of max index 4
        int[] arr = { 1, 2, 3, 4, 5 };

        // Display values of array elements
        for (int i = 0; i < arr.Length; i++) {
            Console.WriteLine(arr[i]);
        }

        try {

            // Try to access invalid index of array
            Console.WriteLine(arr[7]);
            // An exception is thrown upon executing
            // the above line
        }
        catch (IndexOutOfRangeException e) {

            // The Message property of the object
            // of type IndexOutOfRangeException
            // is used to display the type of exception
            // that has occurred to the user.
            Console.WriteLine("An Exception has occurred : {0}", e.Message);
        }
    }
}
```

**输出:**

```cs
1
2
3
4
5
An Exception has occurred : Index was outside the bounds of the array.
```

### 使用多个尝试捕获块

在下面给出的代码中，我们试图在 try 块中生成一个异常，并在多个 catch 块之一中捕获它。当我们不确定可能生成的异常类型时，使用多个 catch 块，因此我们编写不同的块来处理遇到的任何类型的异常。
finally 块是代码中必须执行的部分，不管异常是否生成。在下面给出的程序中，数组的元素显示在 finally 块中。
**语法:**

```cs
try
{
  // statements that may cause an exception
}
catch(Specific_Exception_type obj)
{
  // handler code
}
catch(Specific_Exception_type obj)
{
  // handler code
}
.
.
.
finally
{
  //default code
}
```

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show use of
// multiple try catch blocks
using System;

class Program {

    static void Main(string[] args)
    {
        int[] arr = {19, 0, 75, 52};

        try {

            // Try to generate an exception
            for (int i = 0; i < arr.Length; i++) {
                Console.WriteLine(arr[i] / arr[i + 1]);
            }
        }

        // Catch block for invalid array access
        catch (IndexOutOfRangeException e) {

            Console.WriteLine("An Exception has occurred : {0}", e.Message);
        }

        // Catch block for attempt to divide by zero
        catch (DivideByZeroException e) {

            Console.WriteLine("An Exception has occurred : {0}", e.Message);
        }

        // Catch block for value being out of range
        catch (ArgumentOutOfRangeException e) {

            Console.WriteLine("An Exception has occurred : {0}", e.Message);
        }

        // Finally block
        // Will execute irrespective of the above catch blocks
        finally {
            for (int i = 0; i < arr.Length; i++) {
                Console.Write(" {0}", arr[i]);
            }
        }
    }
}
```

**输出:**

```cs
An Exception has occurred : Attempted to divide by zero.
 19 0 75 52
```

### 用户定义的例外

当我们想要编码一个可能没有被语言定义的异常时，用户定义的异常是有用的。例如，在锅炉房，如果温度上升到某个阈值以上，则必须关闭热量。为了理解用户定义的异常是如何使用的，我们举一个被零除的例子。这里我们定义了一个 DivByZero 类，它继承了 Exception，当分母等于零时，由 DivByZero 操作函数调用。由于对函数的调用可能会引发异常，也可能不会引发异常，因此它被放在 try 块中。定义了一个捕获块来捕获任何异常类型，并且消息属性打印已经发生的异常类型。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to show the user defined exceptions
using System;

// User defined Exception class
// Child of Exception
class DivByZero : Exception {

    // Constructor
    public DivByZero()
    {
        Console.Write("Exception has occurred : ");
    }
}

class Program {

    // Method to perform Division
    public double DivisionOperation(double numerator,
                                 double denominator)
    {
        // throw exception when denominator
        // value is 0
        if (denominator == 0)
            throw new DivByZero();

        // Otherwise return the result of the division
        return numerator / denominator;
    }

    // Main
    static void Main(string[] args)
    {
        Program obj = new Program();
        double num = 9, den = 0, quotient;
        try {
            // Code block that may cause an exception
            quotient = obj.DivisionOperation(num, den);
            Console.WriteLine("Quotient = {0}", quotient);
        }
        // Catch block to catch the generic exception
        catch (Exception e) {
            // Message property of exception object e
            // will give the specific type of the exception
            Console.Write(e.Message);
        }
    }
}
```

**输出:**

```cs
Exception has occurred : Exception of type 'DivByZero' was thrown.
```