# Scala |最终异常

> 原文:[https://www.geeksforgeeks.org/scala-finally-exceptions/](https://www.geeksforgeeks.org/scala-finally-exceptions/)

Scala **最终块**用于执行关闭连接、流或释放资源等重要代码(可以是文件、网络连接、数据库连接等)。不管是否抛出异常，它都会被执行。最后一个区块将在*尝试*和*抓住*区块之后，但在控制权转移回其原点之前执行。
**语法:**

```scala
try {
       //your scala code here    
    } 
finally {
           println("this block of code is always executed")
           // your scala code here, such as to close a database connection
        }

```

**Control flow in try-finally**

在这种情况下，无论 try-block 中是否出现异常，finally 总是会被执行。但是控制流程将取决于 try 块中是否出现异常。

1.  **Exception raised:** Control flow will be finally block followed by default exception handling mechanism If exception has been occurred in try block .
    **Example:**

    ```scala
    // Scala program to demonstrate 
    // control flow of try-finally clause 
    // when exception occur in try block 

    // Creating object
    object GFG 
    { 
        // Main method 
        def main(args: Array[String]) 
        { 
            var arr = new Array[Int](4) 

            try
            { 
                var i = arr(4) 

                // this statement will never execute 
                // as exception is raised by above statement 
                println("Inside try block") 
            } 

            finally
            { 
                println("finally block executed") 
            } 

            // rest program will not execute 
            println("Outside try-finally clause") 

        } 
    }
    ```

    **输出:**

    ```scala
    finally block executed
    ```

2.  **未引发异常:**如果在尝试块中未发生异常，控制流将最终被阻塞，然后是程序的其余部分。
    T3】例:

```scala
// Scala program to demonstrate  
// control flow of try-finally clause 
// when exception doesn't occur in try block 

// Creating object
object GFG 
{ 
    // Main method 
    def main(args: Array[String])  
    { 

      try
        { 
            val str1 = "123".toInt 

            // this statement will execute 
            // as no any exception is raised 
           // by above statement 
            println("Inside try block") 
        } 

        finally
        { 
            println("finally block executed") 
        } 

        // rest program will be executed 
        println("Outside try-finally clause") 
    } 

}
```

**输出:**

```scala
Inside try block
finally block executed
Outside try-finally clause
```

**try-catch-finally clause**

finally 关键字与 try/catch 块结合使用，保证即使抛出异常，也能执行一段代码。
**例:**

```scala
// Scala program of try-catch-finally clause 

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        try
        { 
            // create array
            var array = Array(4, 2, 7) 
            var b = array(5) 
        }
        catch
        { 
            // Catch block contain cases.
            case e: ArithmeticException => println(e) 
            case ex: Exception => println(ex) 
            case th: Throwable=> println("unknown exception"+th) 
        } 
        finally
        { 
            // Finally block will execute
            println("this block always executes") 
        } 

        // rest program will execute 
        println(" rest of code executing") 
    } 
} 
```

**输出**

```scala
java.lang.ArrayIndexOutOfBoundsException: 5
this block always executes
Rest of code executing

```

在上面的例子中，我们在 try block 中创建了一个数组，并从该数组中为变量 b 赋值，但是它抛出了一个异常，因为我们用来为变量 b 赋值的数组索引超出了数组索引的范围。catch block 捕获异常并打印消息，最后，无论发生什么，block 总是会执行。