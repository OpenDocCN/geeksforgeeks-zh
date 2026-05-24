# Scala 中的部分函数

> 原文:[https://www.geeksforgeeks.org/partial-functions-in-scala/](https://www.geeksforgeeks.org/partial-functions-in-scala/)

**简介:**
当一个函数不能为给它的每个变量输入数据产生一个返回，那么这个函数被称为**部分函数**。它只能确定某些实际输入的子集的输出。它只能部分应用于规定的输入。
**一些要点:**

*   部分函数有利于理解许多不一致的 Scala 函数。
*   它可以通过使用案例语句来解释。
*   它是一个特性，需要两种方法即**定义**和**应用**来实现。

**示例:**

```scala
// Scala program of 
// Partial function

// Creating object 
object Case
{

    // Main method
    def main(args: Array[String])
    {

        // Creating Partial function 
        // using two methods
        val r = new PartialFunction[Int, Int] 
        {

            // Applying isDefinedAt method 
            def isDefinedAt(q: Int) = q != 0

            // Applying apply method
            def apply(q: Int) = 12 * q

        } 

        // Displays output if the
        // condition is satisfied
        println(r(10))
    }
}
```

**Output:**

```scala
120

```

这里定义了两种应用分部函数的方法，其中*是定义的*状态条件，如果满足给定条件，*应用*执行操作。
**定义分部函数的方法:**
分部函数有一些定义方法，包括*案例语句**收集方法**然后**or LSE*。

*   **使用 case 语句的分部函数:**
    我们将在下面使用 Case 语句创建分部函数。
    **例:**

```scala
// Scala program using
// case statements

// Creating object 
object Case
{

    // Main method
    def main(args: Array[String])
    {

        // Creating Partial function
        val d: PartialFunction[Int, Int] =
        {

            // using case statement 
            case x if (x % 3) == 0 => x * 3
        }

        // Displays output if 
        // the condition is 
        // satisfied
        println(d(3))
    }
}
```

**Output:**

```scala
9

```

这里，使用 *case* 语句创建分部函数，所以这里不需要*应用*和*定义*。

*   **Partial function using orElse:**
    This method is helpful in chaining Partial functions together.
    **Example:**

    ```scala
    // Scala program using
    // orElse

    // Creating object 
    object orElse
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating Partial function1
            val M: PartialFunction[Int, Int] = 
            {

                // using case statement 
                case x if (x % 5) == 0 => x * 5
            }

            // Creating Partial function2 
            val m: PartialFunction[Int, Int] = 
            {

                // using case statement 
                case y if (y % 2) == 0 => y * 2
            }

            // chaining two partial 
            // functions using orElse 
            val r = M orElse m

            // Displays output for 
            // which the given condition 
            // is satisfied
            println(r(5))
            println(r(4))
        }
    }
    ```

    **Output:**

    ```scala
    25
    8

    ```

    这里，*或*将返回满足给定条件的输出。

    *   **Partial function using Collect method:**
    *Collect* method requests Partial function to every single element of the collection and thus, helps in constructing a new collection.
    **Example:**

    ```scala
    // Scala program using
    // collect method

    // Creating object 
    object Collect
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating Partial function
            val M: PartialFunction[Int, Int] = 
            {

                // using case statement 
                case x if (x % 5) != 0 => x * 5
            }

            // Applying collect method
            val y = List(7, 15, 9) collect { M }

            // Displays output for which 
            // the given condition 
            // is satisfied
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    List(35, 45)

    ```

    这里， *Collect* 将对列表的所有元素应用 Partial 函数，并根据所述条件返回一个新列表。

    *   **Partial function using andThen:**
    This method appends at the end of the chains, which is utilized to continue towards additional chains of Partial functions.
    **Example:**

    ```scala
    // Scala program using
    // andThen method

    // Creating object 
    object andThen
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating Partial function
            val M: PartialFunction[Int, Int] =
            {

                // using case statement 
                case x if (x % 4) != 0 => x * 4
            }

            // Creating another function
            val append = (x: Int) => x * 10

            // Applying andThen method 
            val y = M andThen append

            // Displays output after 
            // appending the another
            // function given
            println(y(7))
        }
    }
    ```

    **Output:**

    ```scala
    280

    ```

    这里，*然后*将把部分函数的输出附加给另一个给定的函数，然后返回那个值。