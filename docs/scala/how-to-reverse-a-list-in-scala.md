# 如何在 scala 中反转列表

> 原文:[https://www . geeksforgeeks . org/如何反转 scala 中的列表/](https://www.geeksforgeeks.org/how-to-reverse-a-list-in-scala/)

在 Scala 中，列表在`scala.collection.immutable`包下定义。列表是包含不可变数据的相同类型元素的集合。我们在 Scala 中使用反转函数来反转一个列表。
以下是反转列表的示例。

*   Reverse a simple list

    ```scala
    // Scala program to reverse a simple Immutable lists 
    import scala.collection.immutable._

    // Creating object 
    object GFG 
    { 
        // Main method 
        def main(args:Array[String]) 
        { 
            // Creating and initializing immutable lists 
            val mylist: List[String] = List("Geeks", "For",
                                    "geeks", "is", "best") 

            // Display the value of mylist1 
            println("Reversed List is: " + mylist.reverse) 

        } 
    } 
    ```

    **输出:**

    ```scala
    Reversed List is: List(best, is, geeks, For, Geeks)
    ```

*   Reverse a list using for loop

    ```scala
    // Scala program to print reverse immutable lists 
    // using for loop
    import scala.collection.immutable._

    // Creating object 
    object GFG
    { 
        // Main method 
        def main(args:Array[String]) 
        { 
            // Creating and initializing immutable lists 
            val mylist: List[String] = List("Geeks", "For", "geeks", "is",
                                            "a", "fabulous", "portal")

            // Display the value of mylist in
            // reverse order using for loop 
            for(element<-mylist.reverse) 
            { 
                println(element) 
            } 
        } 
    } 
    ```

    **输出:**

    ```scala
    portal
    fabulous
    a
    is
    geeks
    For
    Geeks
    ```

*   Reverse a list using foreach loop

    ```scala
    // Scala program to reverse a list
    // using foreach loop
    import scala.collection.immutable._

    // Creating object 
    object GFG
    { 
        // Main method 
        def main(args:Array[String]) 
        { 
            // Creating and initializing immutable lists 
            val mylist = List("Geeks", "For", "geeks", "is",
                            "a", "fabulous", "portal")

            print("Original list is: ")

            // Display the value of mylist using for loop 
            mylist.foreach{x:String => print(x + " ") }

            // calling reverse function
            println("\nReversed list: " + mylist.reverse)
        } 
    } 
    ```

    **输出:**

    ```scala
    Original list is: Geeks For geeks is a fabulous portal 
    Reversed list: List(portal, fabulous, a, is, geeks, For, Geeks)
    ```