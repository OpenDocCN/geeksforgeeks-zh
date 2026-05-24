# 如何在 Scala 中打印列表

> 原文:[https://www.geeksforgeeks.org/how-to-print-a-list-in-scala/](https://www.geeksforgeeks.org/how-to-print-a-list-in-scala/)

在 Scala 中，列表在`scala.collection.immutable`包下定义。列表是包含不可变数据的相同类型元素的集合。

在 Scala 中有多种方法来创建列表。让我们看看如何创建 Scala 列表的一些基本信息。

*   Create an empty List
    **Example :**

    ```scala
    // Scala program to create an empty list 
    import scala.collection.immutable._

    // Creating object 
    object GFG
    { 
        // Main method 
        def main(args:Array[String]) 
        { 

            // Creating an Empty List. 
            val emptylist: List[Nothing] = List() 
            println("The empty list is: " + emptylist) 
        } 
    } 
    ```

    **输出:**

    ```scala
    The empty list is: List()
    ```

*   创建一个简单的列表
    **示例:**

```scala
// Scala program to create a simple Immutable lists 
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating and initializing immutable lists 
        val mylist: List[String] = List("Geeks", "For", "geeks") 

        // Display the value of mylist1 
        println("List is: " + mylist) 

    } 
} 
```

**输出:**

```scala
List is: List(Geeks, For, geeks)
```

*   Using for loop to print elements of List
    **Example :**

    ```scala
    // Scala program to print immutable lists 
    import scala.collection.immutable._

    // Creating object 
    object GFG
    { 
        // Main method 
        def main(args:Array[String]) 
        { 
            // Creating and initializing immutable lists 
            val mylist: List[String] = List("Geeks", "For", 
                                            "geeks", "is",
                                            "a", "fabulous", 
                                            "portal")

            // Display the value of mylist using for loop 
            for(element<-mylist) 
            { 
                println(element) 
            } 
        } 
    } 
    ```

    **输出:**

    ```scala
    Geeks
    For
    geeks
    is
    a
    fabulous
    portal
    ```