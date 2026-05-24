# Scala |调用选项的方法

> 原文:[https://www.geeksforgeeks.org/scala-methods-to-call-option/](https://www.geeksforgeeks.org/scala-methods-to-call-option/)

Scala 中的[选项](https://www.geeksforgeeks.org/scala-option/)是指某一特定类型的单一元素或无元素的载体。当一个方法返回一个甚至可以为空的值时，就使用了 Option，即定义的方法返回一个 Option 的实例，而不是返回单个对象或空值。
有几个方法我们可以调用 Scala *选项*。

*   **def get: A**
    This method is utilized to return an Option’s value.
    **Example:**

    ```scala
    // Scala program of using
    // get method

    // Creating object
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // Using Some class
            val some:Option[Int] = Some(20)

            // Applying get method
            val x = some.get

            // Displays the value 
            println(x)
        }
    }
    ```

    **Output:**

    ```scala
    20

    ```

    在这里， *get* 方法不能应用于 *None* 类，因为它会显示一个异常。

*   **def productArity: Int**
    这个方法是用来返回选项值的大小。
    **例:**

    ```scala
    // Scala program of returning 
    // the size of the value

    // Creating object
    object GFG
    {

        // Main method
        def main(args: Array[String])
        {

            // Using Some class
            val some:Option[Int] = Some(20)

            // Applying productArity
            // method
            val x = some.productArity

            // Displays the size of
            // the Option's value
            println(x)
        }
    }
    ```

    **输出:**

```scala
1

```