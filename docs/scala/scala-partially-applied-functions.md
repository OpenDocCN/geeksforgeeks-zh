# Scala |部分应用的函数

> 原文:[https://www . geesforgeks . org/Scala-部分应用-函数/](https://www.geeksforgeeks.org/scala-partially-applied-functions/)

**部分应用函数**是未应用于所述函数定义的所有参数的函数，即在调用函数时，我们可以提供一些参数，并且在需要时提供剩余的参数。我们调用一个函数，我们可以在其中传递更少的参数，当我们传递更少的参数时，它不会抛出异常。这些没有传递给函数的参数我们使用连字符(_)作为占位符。
**一些重要的点:**

*   部分应用的函数有助于将接受许多参数的函数最小化为只接受一些参数的函数。
*   它可以替换一个函数定义的任意数量的参数。
*   用户更容易利用这种方法。

**语法:**

```scala
val multiply = (a: Int, b: Int, c: Int) => a * b * c

// less arguments passed
val f = multiply(1, 2, _: Int)
```

正如我们在上面的语法中看到的，我们定义了一个普通的函数乘法，它有三个参数，我们传递的参数较少(两个)。我们可以看到它没有抛出部分应用函数的异常。
**例:**

```scala
// Scala program of Partially
// applied functions

// Creating object
object Applied
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a Partially applied
        // function
        def Book(discount: Double, costprice: Double) 
        : Double =
        {

            (1 - discount/100) * costprice

        }

        // Applying only one argument
        val discountedPrice = Book(25, _: Double)

        // Displays discounted price
        // of the book
        println(discountedPrice(400))

    }
}
```

**Output:**

```scala
300.0

```

在这里，*折扣*在参数中传递，*成本价*部分留空，以后需要的时候可以传递，所以折扣价可以计算任意多次。

**部分应用函数的更多例子:**

1.  即使未应用于任何已定义的参数，也可以获得部分应用的函数。
    **例:**

    ```scala
    // Scala program of Partially
    // applied functions

    // Creating object
    object Applied
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating a Partially applied
            // function
            def Mul(x: Double, y: Double)
            : Double =
            {
                x * y
            }

            // Not applying any argument
            val r = Mul _

            // Displays Multiplication
            println(r(9, 8))
        }
    }
    ```

    **输出:**

    ```scala
    72.0

    ```

2.  部分应用的函数可以用来替换任意数量的参数。
    **例:**

    ```scala
    // Scala program of Partially
    // applied functions

    // Creating object
    object Applied
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating a Partially applied
            // function
            def Mul(x: Double, y: Double, z: Double)
            : Double =
            {
                x * y * z
            }

            // applying some arguments
            val r = Mul(7, 8, _ : Double)

            // Displays Multiplication
            println(r(10))
        }
    }
    ```

    **输出:**

    ```scala
    560.0

    ```

3.  *Currying* approach can be utilized in Partially applied functions to transmit a function with multiple arguments into multiple functions, where each function takes only one argument.
    **Example:**

    ```scala
    // Scala program of Partially
    // applied functions using
    // Currying approach

    // Creating object
    object curr
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating a Partially applied
            // function
            def div(x: Double, y: Double) 
            : Double =
            {
                x / y
            }

            // applying currying approach 
            val m = (div _).curried

            // Displays division
            println(m(72)(9))
        }
    }
    ```

    **Output:**

    ```scala
    8.0

    ```

    这里，currying 方法将给定的函数分成两个函数，每个函数取一个参数，因此，您需要为每个函数传递一个值，并获得所需的输出。