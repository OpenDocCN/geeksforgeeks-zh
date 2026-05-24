# 在 scala 中找到列表的最后一个元素

> 原文:[https://www . geesforgeks . org/find-Scala 列表中的最后一个元素/](https://www.geeksforgeeks.org/find-the-last-element-of-a-list-in-scala/)

在 Scala 中，列表在`scala.collection.immutable`包下定义。列表是包含不可变数据的相同类型元素的集合。我们一般使用 **last** 功能打印列表的最后一个元素。

下面是在 Scala 中查找给定列表的最后一个元素的例子。

*   Simply print last element of a list

    ```scala
    // Scala program to find the last element of a given list 
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

            // Display the last value of mylist
            println("Last element is: " + mylist.last) 

        } 
    } 
    ```

    **输出:**

    ```scala
    Last element is: best
    ```

*   Print last element of a list using for loop

    ```scala
    // Scala program to find the last element of a given list
    // using for loop 
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
                                    "a", "fabulous", "portal")

            // Display the last value of mylist using for loop 
            for(element<-mylist.last) 
            { 
                print(element) 
            } 
        } 
    } 
    ```

    **输出:**

    ```scala
    portal
    ```

*   Print last element of a list using foreach loop

    ```scala
    // Scala program to find the last element of a given list
    // using foreach loop 
    import scala.collection.immutable._

    // Creating object 
    object GFG
    { 

        // Main method 
        def main(args:Array[String]) 
        { 
            // Creating and initializing immutable lists 
            val mylist = List(1, 2, 3, 4, 5, 6)

            print("Original list is: ")
            // Display the value of mylist using for loop 
            mylist.foreach{x:Int => print(x + " ") }

            // calling last function
            println("\nLast element is: " + mylist.last)
        } 
    } 
    ```

    **输出:**

    ```scala
    Original list is: 1 2 3 4 5 6 
    Last element is: 6
    ```