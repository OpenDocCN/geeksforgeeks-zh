# 在 Scala 中调用超类构造函数

> 原文:[https://www . geesforgeks . org/calling-a-super-class-constructor-in-Scala/](https://www.geeksforgeeks.org/calling-a-super-class-constructor-in-scala/)

先决条件–[Scala 构造函数](https://www.geeksforgeeks.org/scala-constructors/)

在 Scala 中， ***构造函数*** 用于初始化对象的状态，并在对象创建时执行。只有一个 **[主构造函数](https://www.geeksforgeeks.org/scala-primary-constructor/)** ，所有其他构造函数最终都必须链接到其中。当我们在 Scala 中定义子类时，当我们定义子类声明的扩展部分时，我们控制由它的主构造函数调用的超类构造函数。

*   **With one constructor:** An example of calling a super class constructor
    **Example:**

    ```scala
    // Scala program to illustrate
    // calling a super class constructor

    // Primary constructor
    class GFG (var message: String)
    {
        println(message)
    }

    // Calling the super class constructor
    class Subclass (message: String) extends GFG (message) 
    {
        def display()
        {
            println("Subclass constructor called")
        }
    }

    // Creating object
    object Main 
    { 
        // Main method
        def main(args: Array[String]) 
        { 

            // Creating object of Subclass 
            var obj = new Subclass("Geeksforgeeks"); 
            obj.display();
        } 
    } 
    ```

    **Output:**

    ```scala
    Geeksforgeeks
    Subclass constructor called

    ```

    在上例中，子类被定义为调用 **GFG** 类的主构造函数，它是一个以 ***消息*** 为参数的单参数构造函数。在 Scala 中定义子类时，当定义子类声明的**扩展**段时，控制子类的主构造函数调用的超类构造函数。

*   **With multiple constructors :** In a case with the Superclass having multiple constructors, any of those constructors can be called using the primary constructor of the Subclass. For Example, in the following code, the double argument constructor of the Superclass is called by the primary constructor of the Subclass using the **extends** clause by defining the specific constructor.

    **示例:**

    ```scala
    // Scala program to illustrate
    // calling a specific super class constructor

    // Primary constructor (1)
    class GFG (var message: String, var num: Int)
    {

        println(message+num)

        // Auxiliary constructor (2)
        def this (message: String) 
        {
            this(message, 0)

        }

    }

    // Calling the super class constructor with 2 arguments
    class Subclass (message: String) extends GFG (message, 3000)
    {
        def display()
        {
            println("Subclass constructor called")
        }
    }

    // Creating object
    object GFG 
    { 
        // Main method
        def main(args: Array[String]) 
        { 

            // Creating object of Subclass 
            var obj = new Subclass("Article count "); 
            obj.display();
        } 
    } 
    ```

    **Output:**

    ```scala
    Article count 3000
    Subclass constructor called

    ```

*   我们可以在这里调用单参数构造函数，默认情况下，另一个参数值将是 0。
    **例:**

    ```scala
    // Scala program to illustrate
    // calling a specific super class constructor

    // Primary constructor (1)
    class GFG (var message: String, var num: Int) 
    {

        println(message + num)

        // Auxiliary constructor (2)
        def this (message: String) 
        {
            this(message, 0)

        }

    }

    // Calling the superclass constructor with 2 arguments
    class Subclass (message: String) extends GFG (message) 
    {
        def display()
        {
            println("Subclass constructor called")
        }
    }

    // Creating object
    object GFG 
    { 
        // Main method
        def main(args: Array[String]) 
        { 

            // Creating object of Subclass 
            var obj = new Subclass("Article Count "); 
            obj.display();
        } 
    } 
    ```

    **输出:**

    ```scala
    Article Count 0
    Subclass constructor called

    ```