# Scala | Ranges

> 原文:[https://www.geeksforgeeks.org/scala-ranges/](https://www.geeksforgeeks.org/scala-ranges/)

Scala 中的**范围**可以定义为一系列有组织的均匀分隔的整数。这有助于用更少的方法提供更多的力量，因此，这里执行的操作非常快。

**一些重要的点:**

*   *范围*可以被用于循环迭代。
*   可以使用一些预定义的方法获得，即*到*、*到*、*到*。
*   它由三个常数定义，即(开始、结束和增量值)。

**语法:**

```scala
val range = Range(x, y, z)
```

其中， **x** 为下限， **y** 为上限， **z** 为增量。
**例:**

```scala
// Scala program for Ranges

// Creating object
object GFG
{

    // Main method
    def main(args: Array[String])
    {

        // applying range method
        val x = Range(3, 10, 1)

        // Displays given range
        println(x)

        // Displays starting value
        // of the given range
        println(x(0))

        // Displays last value
        // of the given range
        println(x.last)
    }
}
```

**Output:**

```scala
Range(3, 4, 5, 6, 7, 8, 9)
3
9

```

因此，我们可以说范围的上限是不包含的。

### 在范围上执行的操作

*   If we want a range inclusive of the end value, we can also use the **until** method both until and Range methods are used for the same purpose.
    **Example:**

    ```scala
    // Scala program for Ranges

    // Creating object
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // applying range method
            val x = Range(0, 10, 2)

            // applying until method
            val y = 0 until 10 by 2

            // Displays true if both the 
            // methods are equivalent
            println(x == y)
        }
    }
    ```

    **Output:**

    ```scala
    true

    ```

    这里，**通过**方法执行增量的工作。

*   The upper bound of the *Range* can be made inclusive.
    **Example:**

    ```scala
    // Scala program for Ranges

    // Creating object
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // applying range method
            val x = Range(1, 8)

            // Including upper bound
            val y = x.inclusive

            // Displays all the elements
            // of the range
            println(y)
        }
    }
    ```

    **Output:**

    ```scala
    Range(1, 2, 3, 4, 5, 6, 7, 8)

    ```

    这里，*包括*用于包括范围的上限。

*   If we want a range of integer values, we can use the **to** method both to and inclusive Ranges are equivalent.
    **Example:**

    ```scala
    // Scala program for Ranges

    // Creating object
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // applying range method
            val x = Range(1, 8)

            // Including upper bound
            val y = x.inclusive

            // applying 'to' method
            val z = 1 to 8

            // Displays true if both the
            // methods are equal
            println(y == z)
        }
    }
    ```

    **Output:**

    ```scala
    true

    ```

    因此，这两种方法执行相同的任务。