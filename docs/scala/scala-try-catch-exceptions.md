# Scala |尝试捕捉异常

> 原文:[https://www.geeksforgeeks.org/scala-try-catch-exceptions/](https://www.geeksforgeeks.org/scala-try-catch-exceptions/)

Scala 中的 **Try-Catch** 构造与 Java 中的不同，Scala 中的 Try-Catch 是一个表达式。Scala 在 catch 子句中使用了[模式匹配](https://www.geeksforgeeks.org/scala-pattern-matching/)。假设，我们必须实现一系列可以抛出异常的代码，如果我们想要控制该异常，那么我们应该利用 Try-Catch 段，因为它允许我们只在一个块中尝试捕获每一种类型的异常，我们需要在 Catch 中编写一系列 case 语句，因为 Scala 使用匹配来分析和处理异常。

*   **Example :**

    ```scala
    // Scala program of try-catch
    // exception

    // Creating object
    object Arithmetic
    {

    // Main method
    def main(args: Array[String]) 
    {

        // Try clause
        try
        {
            // Dividing a number
            val result = 11/0
        }

        // Catch clause
        catch
        { 
                // Case statement
                case x: ArithmeticException => 
                { 

                // Display this if exception is found
                println("Exception: A number is not divisible by zero.")
            }
        }
    }
    }
    ```

    **Output:**

    ```scala
    Exception: A number is not divisible by zero.

    ```

    这里，当一个数不能被零整除时，抛出一个异常。

*   **Example :**

    ```scala
    // Scala program of Try-Catch
    // Exception
    import java.io.FileReader
    import java.io.FileNotFoundException
    import java.io.IOException 

    // Creating object
    object GfG
    {

    // Main method
    def main(args: Array[String]) 
    {

        // Try clause
        try
        {
            // Creating object for FileReader
            val t = new FileReader("input.txt")
        } 

        // Catch clause
        catch
        {

            // Case statement-1
            case x: FileNotFoundException =>
            {
                // Displays this if the file is
                // missing
                println("Exception: File missing")

            }

            // Case statement-2
            case x: IOException   => 
            {

                // Displays this if input/output 
                // exception is found
                println("Input/output Exception")

            }
        }
    }
    }
    ```

    **Output:**

    ```scala
    Exception: File missing

    ```

    在这里，首先执行 try 块，如果抛出任何异常，则检查 catch 子句的每个情况，匹配抛出的异常的情况作为输出返回。