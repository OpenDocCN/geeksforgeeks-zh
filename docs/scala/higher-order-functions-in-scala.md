# Scala 中的高阶函数

> 原文:[https://www . geeksforgeeks . org/高阶函数 in-scala/](https://www.geeksforgeeks.org/higher-order-functions-in-scala/)

如果一个函数包含其他函数作为参数或返回一个函数作为输出，即与其他函数一起运行的函数称为高阶函数，则该函数称为**高阶函数**。值得了解的是，这种高阶函数也适用于以函数为参数或作为结果返回函数的函数和方法。这是可行的，因为 Scala 的编译器允许将方法强制转换成函数。
**高阶函数的几个要点:**

*   *高阶函数*是可能的，因为 Scala 编程语言将函数作为一级值处理，这意味着类似于一些其他值，函数甚至可以作为参数传递或作为输出返回，这有助于为编写代码提供一种可调整的方法。
*   这有利于产生函数组合，其中函数可以由另一个函数形成。函数组合是一种组合方法，其中一个函数显示两个组合函数的使用情况。
*   它在创建 lambda 函数或匿名函数时也是有建设性的。[匿名函数](https://www.geeksforgeeks.org/anonymous-functions-in-scala/)是没有名字的函数，虽然执行起来像一个函数。
*   它甚至被用于最小化程序中的冗余代码行。

现在，让我们看一些例子。

*   **Example :**

    ```scala
    // Scala program of higher order
    // function

    // Creating object
    object GfG 
    {

        // Main method
        def main(args: Array[String]) 
        {
            // Displays output by assigning 
            // value and calling functions
            println(apply(format, 32))

        }

        // A higher order function
        def apply(x: Double => String, y: Double) = x(y)

        // Defining a function for
        // the format and using a
        // method toString()
        def format[R](z: R) = "{" + z.toString() + "}"

    }
    ```

    **Output:**

    ```scala
    {32.0}

    ```

    这里，应用函数包含另一个函数 **x** ，其值为 **y** ，并将函数 x 应用于 y。

*   **Example :**

    ```scala
    // Scala program of higher order
    // function

    // Creating object
    object GfG 
    {
        // Main method
        def main(args: Array[String]) 
        {

            // Creating a list of numbers
            val num = List(7, 8, 9)

            // Defining a method
            def multiplyValue = (y: Int) => y * 3

            // Creating a higher order function 
            // that is assigned to the variable
            val result = num.map(y => multiplyValue(y))

            // Displays output
            println("Multiplied List is: " + result)
        }
    }
    ```

    **Output:**

    ```scala
    Multiplied List is: List(21, 24, 27)

    ```

    这里，*映射*是以另一个函数即(y = >多值(y))为参数的函数，所以是高阶函数。