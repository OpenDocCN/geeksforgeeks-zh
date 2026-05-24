# C# |如何使用多 catch 子句

> 原文:[https://www . geesforgeks . org/c-sharp-how-to-multi-catch-子句/](https://www.geeksforgeeks.org/c-sharp-how-to-use-multiple-catch-clause/)

catch 块的主要目的是处理 try 块中引发的异常。只有当程序中出现异常时，该块才会执行。
在 C# 中，可以使用多个 catch 块和 try 块。通常，多个 catch 块用于处理不同类型的异常，这意味着每个 catch 块用于处理不同类型的异常。如果您对同一类型的异常使用多个 catch 块，那么它会给您一个编译时错误，因为 **C# 不允许您对同一类型的异常使用多个 catch 块**。catch 块的前面总是有 try 块。

一般来说，catch 块按照它们在程序中出现的顺序进行检查。如果给定类型的异常与第一个 catch 块匹配，则执行第一个 catch 块，其余的 catch 块被忽略。并且如果起始 catch 块不适合异常类型，那么编译器搜索下一个 catch 块。

**语法:**

```cs
try {

// Your code 

}

// 1st catch block
catch(Exception_Name) {

// Code

}

// 2nd catch block
catch(Exception_Name) {

// Code

}

.
.
.
.

```

下面给出了一些例子，以便更好地理解实现:

**示例 1:** 在下面的示例中，try block 生成两种不同类型的异常，即 **DivideByZeroException** 和 **IndexOutOfRangeException** 。现在，我们使用两个 catch 块来处理这些与单个 try 块相关联的异常。每个 catch 块捕获不同类型的异常，比如 catch 块 1 用于捕获 DivideByZeroException，catch 块 2 用于捕获 IndexOutOfRangeException。

```cs
// C# program to illustrate the
// use of multiple catch block
using System;

class GFG {

    // Main Method
    static void Main()
    {

        // Here, number is greater than divisor
        int[] number = { 8, 17, 24, 5, 25 };
        int[] divisor = { 2, 0, 0, 5 };

        // --------- try block ---------

        for (int j = 0; j < number.Length; j++)

            // Here this block raises two different
            // types of exception, i.e. DivideByZeroException
            // and IndexOutOfRangeException
            try {

                Console.WriteLine("Number: " + number[j]);
                Console.WriteLine("Divisor: " + divisor[j]);
                Console.WriteLine("Quotient: " + number[j] / divisor[j]);
            }

            // Catch block 1

            // This Catch block is for
            // handling DivideByZeroException
            catch (DivideByZeroException) {

                Console.WriteLine("Not possible to Divide by zero");
            }

            // Catch block 2

            // This Catch block is for
            // handling IndexOutOfRangeException
            catch (IndexOutOfRangeException) {
                Console.WriteLine("Index is Out of Range");
            }
    }
}
```

**Output:**

```cs
Number: 8
Divisor: 2
Quotient: 4
Number: 17
Divisor: 0
Not possible to Divide by zero
Number: 24
Divisor: 0
Not possible to Divide by zero
Number: 5
Divisor: 5
Quotient: 1
Number: 25
Index is Out of Range

```

**示例 2:** 在下面的示例中，尝试阻止引发异常。因此，我们将使用三种不同类型的 catch 块来处理 try 块引发的异常。捕捉块 1 将处理**指数超出范围异常**，捕捉块 2 将处理**格式异常**，捕捉块 3 将处理**超出范围异常**。

```cs
// C# program to illustrate the concept
// of multiple catch clause
using System;

class GFG {

    // Main method
    static void Main()
    {

        // This block raises an exception
        try {

            byte data = byte.Parse("a");
            Console.WriteLine(data);
        }

        // Catch block 1

        // This block is used to handle
        // IndexOutOfRangeException type exception
        catch (IndexOutOfRangeException) {

            Console.WriteLine("At least provide one Argument!");
        }

        // Catch block 2

        // This block is used to handle
        // FormatException type exception
        catch (FormatException) {

            Console.WriteLine("Entered value in not a number!");
        }

        // Catch block 3

        // This block is used to handle
        // OverflowException type exception
        catch (OverflowException) {

            Console.WriteLine("Data is out of Range!");
        }
    }
}
```

**Output:**

```cs
Entered value in not a number!

```