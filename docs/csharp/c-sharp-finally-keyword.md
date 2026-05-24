# C# |最后关键词

> 原文:[https://www.geeksforgeeks.org/c-sharp-finally-keyword/](https://www.geeksforgeeks.org/c-sharp-finally-keyword/)

在编程中，有时异常可能会导致错误，从而结束当前方法。但是，该方法可能打开了需要关闭的文件或网络。因此，为了克服这类问题，C# 提供了一个特殊的关键字，命名为 finally 关键字。这是 C# 中的保留关键字。
当 try/catch 块离开执行时，finally 块将执行，不管是什么条件导致的。**无论 try 块正常终止还是由于异常而终止，它总是执行。**finally block 的主要目的是释放系统资源。最后一个块跟随 try/catch 块。

**语法:**

```cs
try {

    // code...
}

// this is optional
catch {

   // code..
}

finally
{
    // code..
}

```

**要点:**

*   在 C# 中，不允许在同一个程序中有多个 finally 块。
*   final 块不包含任何 return、continue、break 语句，因为它不允许控件离开 final 块。
*   您也可以使用 finally block，只使用 try block，这意味着不使用 catch block，但是在这种情况下，不会处理任何异常。
*   finally 块将在 try 和 catch 块之后，但在控制转移回其原点之前执行。

**例 1:**

```cs
// C# program to demonstrate finally
using System;

class Geek {

    // A method that throws an
    // exception and has finally. 
    // This method will be called
    // inside try-catch. 
    static void A() 
    { 
        try {

            Console.WriteLine("Inside A"); 
            throw new Exception("Throwing Exception");
        } 

        finally
        { 
            Console.WriteLine("A's finally"); 
        } 
    } 

    // This method also calls
    // finally. This method 
    // will be called outside
    // try-catch. 
    static void B() 
    { 

        try { 

            Console.WriteLine("Inside B"); 
            return; 
        } 

        finally
        { 
            Console.WriteLine("B's finally"); 
        } 
    } 

// Main Method
public static void Main(String[] args) 
{ 
    try { 

        A(); 
    } 

    catch (Exception) { 

        Console.WriteLine("Exception Caught"); 
    } 
    B(); 
} 
} 
```

**输出:**

```cs
Inside A
A's finally
Exception Caught
Inside B
B's finally

```

**示例 2:** 使用带有已处理异常的最终块

```cs
// C# program to illustrate the finally
// block with handled exception
using System;

public class GFG {

    // Main Method
    static public void Main()
    {

        // variables
        int number = 4;
        int divisor = 0;

        // try block
        // This block raise exception
        try {

            int output = number / divisor;
        }

        // catch block
        // This block handle exception
        catch (DivideByZeroException) {

            Console.WriteLine("Not possible to divide by zero!");
        }

        // finally block
        // This block release the 
        // resources of the system
        // and this block always executes
        finally {

            Console.WriteLine("Finally Block!");
        }
    }
}
```

**输出:**

```cs
Not possible to divide by zero!
Finally Block!

```

**解释:**在上面的示例中，在 try 块内生成了一个异常(DivideByZeroException)，该异常被与 try 块关联的 catch 块捕获。现在，在 try-catch 块离开它们的执行之后，最后块执行并释放 try-catch 块使用的系统资源。

**示例 3:** 使用带有未处理异常的最终块

```cs
// C# program illustrate the finally
// block with unhandled exception
using System;

public class GFG {

    // Main method
    static public void Main () {

    // variables
    int number = 4;
    int divisor = 0;
    int output;    

    // In this block exception raise
    // Here this exception in unhandled
    // due to the absence of catch block
    try
    {
         output = number/divisor;      
    }

    // finally block, this block always
    // executes 
    finally
    {
        Console.WriteLine("Finally Block!");
    }
    }
}
```

**输出:**

```cs
Finally Block!
```

**运行时错误:**

> 未处理异常:
> 系统。DivideByZeroException:试图除以零。
> 在 GFG。主()在:0
> 【错误】致命的未处理异常:系统。DivideByZeroException:试图除以零。
> 在 GFG。0 中的 Main()

**解释:**在本例中，在 try 块内生成了一个异常(DivideByZeroException)，但由于与 try 块相关联的 catch 块不存在，因此不会处理。在这种情况下，当 try 块退出执行时，最后块执行并释放系统资源。这意味着 finally block 不关心异常是否被处理。