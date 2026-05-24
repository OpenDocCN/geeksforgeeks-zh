# Scala | Tuple

> 原文:[https://www.geeksforgeeks.org/scala-tuple/](https://www.geeksforgeeks.org/scala-tuple/)

**元组**是元素的集合。元组是异构数据结构，即它们可以存储不同数据类型的元素。元组是*不可变的*，不像 scala 中的数组是可变的。
存储整数、字符串和布尔值的元组的示例。

```scala
val name = (15, "Chandan", true)

```

元组的类型由它包含的元素的数量和这些元素的数据类型来定义。

**例如:**

```scala
// this is tuple of type Tuple3[ Int, String, Boolean ] 
val name = (15, "Chandan", true)

```

设 N 为元组中元素的个数。Scala 目前在一个元组中被限制为 22 个元素，也就是说 N 应该是， **1 < =N < =22** ，元组最多可以有 22 个元素，如果元素数量超过 22，那么就会产生错误。然而，我们可以使用嵌套元组来克服这个限制(注意，一个元组可以包含其他元组)

**Operations on tuple**

1.  **从元组访问元素:**可以使用*下划线*语法、方法 **tup 来访问元组元素。_i** 用于访问元组的 ith 元素。
    **例:**

```scala
// Scala program to access 
// element using underscore method

// Creating object
object gfg 
{
    // Main method
    def main(args: Array[String]) 
    {

        var name = (15, "chandan", true)

        println(name._1) // print 1st element
        println(name._2) // print 2st element
        println(name._3) // print 3st element
    }
}
```

**Output:**

```scala
15
chandan
true

```

*   **Pattern matching on tuples :** Pattern matching is a mechanism for checking a value against a pattern. A successful match can also deconstruct a value into its constituent parts.
    **Example :**

    ```scala
    // Scala program of pattern matching on tuples

    // Creating object
    object gfg 
    {
        // Main method
        def main(args: Array[String]) 
        {
            var (a, b, c) = (15, "chandan", true)
            println(a)
            println(b)
            println(c)
        }
    }
    ```

    **Output:**

    ```scala
    15
    chandan
    true

    ```

    在上面的例子中，var (a，b，c)= (15，“chandan”，true)表达式赋值 a = 15，b =“chandan”，c = true。

    *   **迭代元组:**要迭代元组，使用 **tuple.productIterator()** 方法。
    **示例:**

    ```scala
    // Scala program to iterate over tuples
    // using productIterator method

    // Creating object
    object gfg 
    {
        // Main method
        def main(args: Array[String]) 
        {
            var name = (15, "chandan", true)

            // The foreach method takes a function
            // as parameter and applies it to 
            // every element in the collection
            name.productIterator.foreach{i=>println(i)}
        }
    }
    ```

    **输出:**

    ```scala
    15
    chandan
    true

    ```

    *   **将元组转换为字符串:**将元组转换为字符串会将其所有元素串联成一个字符串。我们对此使用 **tuple.toString()** 方法。
    **示例:**

    ```scala
    // Scala program to convert tuple element to String

    // Creating object
    object gfg
    {
        // Main method
        def main(args: Array[String])
        {
            val name = (15, "chandan", true)

            // print converted string
            println(name.toString() )
        }   
    }
    ```

    **输出:**

    ```scala
    (15, chandan, true)

    ```

    *   **交换元组的元素:**交换元组的元素我们可以使用**元组.交换**方法。
    **示例:**

    ```scala
    // Scala program to swap tuple element

    // Creating object
    object gfg 
    {
        // Main method
        def main(args: Array[String]) 
        {
            val name = ("geeksforgeeks","gfg")

            // print swapped element
            println(name.swap)
        }
    }
    ```

    **输出:**

    ```scala
    (Geeksquize,geeksforgeeks)

    ```