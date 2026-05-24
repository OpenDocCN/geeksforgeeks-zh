# Scala |任一

> 原文:[https://www.geeksforgeeks.org/scala-either/](https://www.geeksforgeeks.org/scala-either/)

在 Scala 中**或者**，功能完全类似于 [*选项*](https://www.geeksforgeeks.org/scala-option/) 。唯一不同的是，无论使用哪种方法，都可以返回一个字符串，该字符串可以解释关于出现的错误的指令。*或者*有两个孩子，分别命名为*右*和*左*，其中 ***右*** 类似于*部分*班， ***左**T21】与*无*班相同。左侧用于失败，我们可以返回发生在“非此即彼”子级中的错误，右侧用于成功。
**例:***

```scala
 Either[String, Int]
```

这里，*字符串*用于任一的*左*子作为任一的左参数， *Int* 用于任一的*右*子作为任一的右参数。现在，让我们借助一些例子来详细讨论一下。

*   **Example :**

    ```scala
    // Scala program of Either

    // Creating object and inheriting
    // main method of the trait App
    object GfG extends App
    {

        // Defining a method and applying 
        // Either
        def Name(name: String): Either[String, String] =
        {

            if (name.isEmpty) 
                // Left child for failure
                Left("There is no name.")

            else
                // Right child for success
                Right(name)
        }

        // Displays this if name is 
        // not empty
        println(Name("GeeksforGeeks"))

        // Displays the String present
        // in the Left child 
        println(Name(""))
    }
    ```

    **Output:**

    ```scala
    Right(GeeksforGeeks)
    Left(There is no name.)

    ```

    这里，*是空的*方法检查名称的字段是空的还是填充的，如果它是空的，那么 Left 子对象将返回它自己内部的字符串，如果这个字段不是空的，那么 Right 子对象将返回指定的名称。

*   **Example :**

    ```scala
    // Scala program of Either with
    // Pattern matching

    // Creating object and inheriting
    // main method of the trait App
    object either extends App
    {

        // Defining a method and applying 
        // Either
        def Division(q: Int, r: Int): Either[String, Int] =
        {
            if (q == 0) 
                // Left child for failure 
                Left("Division not possible.")
            else
                // Right child for success
                Right(q / r)
        }

        // Assigning values 
        val x = Division(4, 2)

        // Applying pattern matching
        x match
        {
            case Left(l) => 

            // Displays this if the division
            // is not possible
            println("Left: " + l)

            case Right(r) => 

            // Displays this if division 
            // is possible
            println("Right: " + r)
        }
    }
    ```

    **Output:**

    ```scala
    Right: 2

    ```

    在这里，除法是可能的，这意味着成功，所以*右*返回 2。这里，我们在这个例子中使用了模式匹配。