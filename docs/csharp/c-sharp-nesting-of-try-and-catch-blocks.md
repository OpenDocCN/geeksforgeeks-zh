# C# |试捕块嵌套

> 原文:[https://www . geesforgeks . org/c-sharp-试捕块嵌套/](https://www.geeksforgeeks.org/c-sharp-nesting-of-try-and-catch-blocks/)

在 C# 中，允许嵌套 try & catch 块。try 块的嵌套意味着一个 try 块可以嵌套到另一个 try 块中。不同的程序员使用外部 try 块处理严重的异常，而内部块处理正常的异常。

**注:**

*   如果在内部 try 块中引发异常，而该异常未被与 try 块关联的 catch 块捕获，则该异常将被提升到外部 try 块。通常，嵌套的 try 块用于允许以不同的方式处理不同的错误组。
*   这是一个必要条件，即 try 块后面必须跟一个 catch 或 finally 块，因为如果使用不带 catch 或 finally 的 try 块，那么就会出现编译时错误。

**语法:**

```cs
// outer try block
try
{

   // inner try block
   try
     {
       // code...
     }

   // inner catch block
   catch
     {
       // code...
     }
}

// outer catch block
catch
  {
    // code...
  }

```

下面给出了一些例子，以便更好地理解实现:

**示例 1:** 在该程序中， **DivideByZeroException** 在内部尝试块中生成，该内部尝试块被与内部尝试块相关联的 catch 块捕获，并继续程序的流程。当**indexoutofrangerexception**在内部尝试块内生成未被内部捕获块捕获的异常时，内部尝试块将该异常转移到外部尝试块。之后，与外部 try 块关联的 catch 块捕获导致程序终止的异常。这里对于 **17/0** 和 **24/0** 内部试块正在执行，但是对于编号 **25** 外部试块正在执行。

```cs
// C# program to illustrate how outer
// try block will handle the exception
// which is not handled by the inner 
// try catch block
using System;

class GFG {

    // Main Method
    static void Main()
    {

        // Here, number is greater
        // than divisor.
        int[] number = {8, 17, 24, 5, 25};
        int[] divisor = {2, 0, 0, 5};

        // Outer try block

        // Here IndexOutOfRangeException occurs
        // due to which program may terminates
        try {

            for (int j = 0; j < number.Length; j++) {

                // Inner try block

                // Here DivideByZeroException caught
                // and allow the program to continue 
                // its execution

                try {

                    Console.WriteLine("Number: " + number[j] + 
                                      "\nDivisor: " + divisor[j] + 
                                      "\nQuotient: " + number[j] / divisor[j]);
                }

                // Catch block for inner try block
                catch (DivideByZeroException) {

                    Console.WriteLine("Inner Try Catch Block");
                }
            }
        }

        // Catch block for outer try block
        catch (IndexOutOfRangeException) {

            Console.WriteLine("Outer Try Catch Block");

        }
    }
}
```

**Output:**

```cs
Number: 8
Divisor: 2
Quotient: 4
Inner Try Catch Block
Inner Try Catch Block
Number: 5
Divisor: 5
Quotient: 1
Outer Try Catch Block

```

**示例 2:** 在下面的示例中，在内部尝试块内生成异常，该异常被与内部尝试块相关联的 catch 块捕获。

```cs
// C# program to illustrate
// nested try block
using System;

public class Geeks {

    public string Author_name
    {
        get;
        set;
    }
}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        Geeks str1 = null;

        // outer try block
        try {

            // inner try block
            try {

                str1.Author_name = "";
            }

            // catch block for the inner try block
            catch {

                Console.WriteLine("Inner try catch block");
            }
        }

        // catch block for the outer try block
        catch {

            Console.WriteLine("Outer try catch block");
        }
    }
}
```

**Output:**

```cs
Inner try catch block

```