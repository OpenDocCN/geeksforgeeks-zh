# Scala 控制台| println、printf 和 readLine

> 原文:[https://www . geesforgeks . org/Scala-console-println-printf-and-readline/](https://www.geeksforgeeks.org/scala-console-println-printf-and-readline/)

**控制台**实现在终端显示设定值的功能，即通过*打印*、*打印*、*打印*我们可以发布到显示器上。它还可以通过 scala.io.StdIn 函数从控制台读取值，甚至有助于构建交互式程序。
我们来详细讨论一下，也来看一些与之相关的例子。

*   **println:**
    它用于将值放入控制台，此外还计算尾随换行符。我们可以传递任何类型的参数给它。
*   **Print:**
    它相当于 println，但不计算任何尾随行。它将数据放到行首。
*   **printf:**
    This is helpful in writing format strings and also places extra arguments.
    **Example:**

    ```scala
    // Scala program of print
    // functions

    // Creating an object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Applying console with println
            Console.println("GeeksfoGeeks")

            // Displays output with no
            // trailing lines
            print("CS")
            print("_portal")

            // Used for a newline
            println()

            // Displays format string
            printf("Age = %d", 24)
        }
    }
    ```

    **Output:**

    ```scala
    GeeksfoGeeks
    CS_portal
    Age = 24

    ```

    println 和 Console.println 都是等价的。

*   **readLine():**
    It is a method in which user gives inputs in the pattern of String from the keyboard.
    **Example:**

    ```scala
    // Scala program of readLine()
    // method

    // Creating an object
    object GfG

    {
    // Main method
    def main(args: Array[String]) 

    {
    // Applying a loop
    while (true) {

        // Reads the line from the Console
        val result = scala.io.StdIn.readLine()

        // Displays the string that is 
        // given by the user
        printf("Enter the String: %s", result)

        //prints newline
        println()
         }
       }
    }
    ```

    **Output:**

    ```scala
    //giving user defined inputs
    GfG 
    //output by readline
    Enter the String: Gfg 
    //again giving inputs
    Nidhi 
    //output
    Enter the String: Nidhi 

    ```

    这里，while 循环本质上是无限的，在给出用户输入之后，变量将包含那个(GfG)字符串，如果我们再次给出任何输入，那么变量将包含那个(Nidhi)输入。