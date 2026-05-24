# Scala 中的抽象类

> 原文:[https://www.geeksforgeeks.org/abstract-classes-in-scala/](https://www.geeksforgeeks.org/abstract-classes-in-scala/)

**抽象**是隐藏内部细节，只显示功能的过程。在 Scala 中，抽象是通过使用抽象类来实现的。Scala 抽象类的工作类似于 [Java 抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)。在 Scala 中，抽象类是使用*抽象关键字*构建的。它包含抽象和非抽象方法，并且不能支持多重继承。一个类只能扩展一个抽象类。
**语法:**

```scala
abstract class class_name
{
// code..
}
```

抽象类的抽象方法是那些不包含任何实现的方法。或者换句话说，不包含主体的方法被称为抽象方法。
**语法:**

```scala
def function_name()
```

**示例:**

```scala
// Scala program to illustrate how to 
// create an abstract class

// Abstract class
abstract class myauthor
{

    // abstract method
    def details()
}

// GFG class extends abstract class
class GFG extends myauthor
{
    def details()
    {
        println("Author name: Ankita Saini")
        println("Topic name: Abstract class in Scala")
    }
}

object Main 
{
    // Main method
    def main(args: Array[String]) 
    {
        // objects of GFG class
        var obj = new GFG()
        obj.details()
    }
}
```

**输出:**

```scala
Author name: Ankita Saini
Topic name: Abstract class in Scala

```

**以下是关于 Scala 中抽象类的一些重要观察。**

*   Like Java, in Scala, we are not allowed to create the instance of the abstract class. If we try to create objects of the abstract class, then the compiler will give an error as shown in the below program.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // the concept of abstract class

    // Abstract class
    abstract class myauthor{

        // abstract method
        def details()
    }

    object Main {

        // Main method
        def main(args: Array[String]) {

            // Object of myauthor class
        var obj = new myauthor()
        }
    }
    ```

    **输出:**

    > prog.scala:18:错误:类 myauthor 是抽象的；无法实例化
    > var obj = new myauthor()
    > ^
    > 发现一个错误

*   In Scala, an abstract class can also contain fields. These fields are accessed by the abstract class methods and by the methods of the class which inherit abstract class. As shown in the below program.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // the concept of abstract class

    // Abstract class with fields
    abstract class Geek
    {
        var name : String = "GeeksforGeeks"
        var tutorial: String = "Scala"
        def portal()
    }

    // GFG class extends abstract class
    class GFG extends Geek
    {

        // Abstract class method accessing
        // fields of the abstract class
        def portal()
        {
            println("Portal name: " + name)

        }

        // GFG class method accessing 
        // fields of the abstract class
        def tutdetails()
        {
            println("Tutorial name: " + tutorial) 
        }
    }

    object Main 
    {

        // Main method
        def main(args: Array[String]) 
        {

            // objects of GFG class
            var obj = new GFG()
            obj.portal()
            obj.tutdetails()
        }
    }
    ```

    **输出:**

    ```scala
    Portal name: GeeksforGeeks
    Tutorial name: Scala
    ```

*   Like Java, In Scala, an abstract class can also contain a constructor and a constructor of an abstract class is called when an instance of a inherited class is created. As shown in the below program.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // the concept of abstract class

    // Abstract class with constructor
    // And the constructor contain two arguments
    abstract class myauthor(name: String,
                            topic: String)
    {
        def details()
    }

    // GFG class extends abstract class
    class GFG(name: String, topic: String) extends
                                myauthor(name, topic)
    {
        def details()
        {
            println("Author name: " + name)
            println("Topic name: " + topic)
        }
    }

    object Main 
    {

        // Main method
        def main(args: Array[String])
        {

            // objects of GFG class
            var obj = new GFG("Ankita", "Abstract class")
            obj.details()
        }
    }
    ```

    **输出:**

    ```scala
    Author name: Ankita
    Topic name: Abstract class

    ```

*   An abstract class can also contain only non- abstract method. This allows us to create classes that cannot be instantiated, but can only be inherited. As shown in the below program.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // the concept of abstract class

    // Abstract class with 
    // non-abstract method
    abstract class myauthor
    {

        // Non-abstract method
        def details()
        {
            println("Welcome to GeeksforGeeks")
        }
    }

    // GFG class extends abstract class
    class GFG extends myauthor{}

    object Main 
    {

        // Main method
        def main(args: Array[String])
        {

            // objects of GFG class
            var obj = new GFG()
            obj.details()
        }
    }
    ```

    **输出:**

    ```scala
    Welcome to GeeksforGeeks

    ```

*   In Scala, an abstract class can contain final methods (methods that cannot be overridden). For example, the following program compiles and runs without an error. In Scala, final method is created using final keyword.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // the concept of abstract class

    // Abstract class with the final method
    abstract class myauthor
    {
        final def mymethod()
        {
            println("Final method")
        }
    }

    // GFG class extends abstract class
    class GFG extends myauthor{}

    object Main 
    {

        // Main method
        def main(args: Array[String]) 
        {

            // objects of GFG class
            var obj = new GFG()
            obj.mymethod()
        }
    }
    ```

    **输出:**

    ```scala
    Final method

    ```

**在 Scala 中什么时候使用抽象类:**
一个抽象类是有用的:

*   当我们想要构造一个需要构造函数参数的基类时。
*   什么时候我们的代码会从 Java 代码中调用。

**注:**性状也用于实现抽象。