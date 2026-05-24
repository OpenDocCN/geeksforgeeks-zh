# Scala | Null、Null、Nil、Nothing、None 和 Unit

> 原文:[https://www . geesforgeks . org/Scala-null-null-nil-noth-none-and-unit/](https://www.geeksforgeeks.org/scala-null-null-nil-nothing-none-and-unit/)

Scala 中的空值由 *Null* 、 *null* 、 *Nil* 、 *Nothing* 、 *None* 和 *Unit* 表示。这些空值的解释如下:

*   **null:**
    Objects、Strings 等引用类型可以是*null【2】，Int、Double、Long 等值类型不能是 *null* ，Scala 中的 *null* 类似于 Java 中的 *null* 。*
*   **Null:**
    It is a Trait, which is a subset of each of the reference types but is not at all a sub-type of value types and a single instance of *Null* is *null*. The reference types can be assigned *null* but the value types cannot be assigned *null*.
    **Example :**

    ```scala
    // Scala program using Null and null

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {
            // Method that takes a parameter of type Null
            def usingnull(thing: Null): Unit = 
            { 
                println("GeeksForGeeks"); 
            }

            /*error: type mismatch;

            found   : java.lang.String("hey")

            required: Null*/
            //usingnull("hey")

            // passing null itself
            usingnull(null)
        }
    }
    ```

    **输出:**

    ```scala
    GeeksForGeeks
    ```

    这里，方法*使用由类型为 null 的参数组成的 null* ，我们只能传递两件事。null 本身或 Null 类型的引用。当我们传递一个字符串作为参数时，它不起作用并产生了一个错误。

*   **无:**
    *无*也是特质，没有实例。它是每种不同类型的子集。这个特性的主要动机是为那些总是抛出异常的方法提供一个返回类型，也就是说，通常甚至没有一次返回。也有助于提供*无*的类型。
*   **Unit:**
    The *Unit* is Scala is analogous to the *void* in Java, which is utilized as a return type of a functions that is used with a function when the stated function does not returns anything.
    **Example :**

    ```scala
    // Scala program using Unit type

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {
            // Method return type is unit
            def printNumber(num: (Int) => Unit) = 
            {

                num(1); 
                num(2); 
                num(3);
            }

            printNumber(println)
        }
    }
    ```

    **输出:**

    ```scala
    1
    2
    3
    ```

    这里，方法*打印号*取一个名为*号*的参数，其类型为 **(Int) = >单元**。这意味着 num 是一个由 Int 类型的单个参数组成的方法。方法 *printNumber* 返回 Unit 的类型，也就是说 num 不应该返回值。

*   **Nil:**
    *Nil* is Considered as a List which has zero elements in it. The type of *Nil* is List[Nothing] and as stated above, that *Nothing* has no instances, we can have a List which is confirmed to be desolated.
    **Example:**

    ```scala
    // Scala program to show that
    // Nil is an empty list

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Displays empty list
            println(Nil)
        }
    }
    ```

    **输出:**

    ```scala
    List()
    ```

    因此，我们可以看到返回了一个空列表。

*   **None:**
    It is one of the children of Scala’s Option class which is utilized to avoid assignment of *null* to the reference types. lets see some examples.

    **示例:**

    ```scala
    // Scala program to convert
    // None to empty list

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Displays empty list
            println(None.toList)
        }
    }
    ```

    **输出:**

    ```scala
    List()
    ```

    这里，返回一个空列表。

    **示例:**

    ```scala
    // Scala program to test if
    // None is empty or not

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Displays true if empty
            // else false
            println(None.isEmpty)
        }
    }
    ```

    **输出:**

    ```scala
    true
    ```

    因此，我们可以说*无*为空，返回真。

    **示例:**

    ```scala
    // Scala program to convert None
    // to String

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {

            // Displays String
            println(None.toString)
        }
    }
    ```

    **输出:**

    ```scala
    None
    ```

    因此，没有一个可以转换成字符串。

    **示例:**

    ```scala
    // Scala program of utilizing
    // None with Scala's Option

    // Creating object
    object GfG
    {

        // Main method
        def main(args: Array[String]) 
        {
            // Applying None with 
            // Scala's Option
            val p: Option[String] = None

            // Displays output
            println(p)
        }
    }
    ```

    **输出:**

    ```scala
    None
    ```

    有关该示例的更多信息，请参见 [Scala 的选项](https://www.geeksforgeeks.org/scala-option/)。