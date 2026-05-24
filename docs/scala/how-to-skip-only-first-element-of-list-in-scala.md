# 如何在 Scala 中只跳过 List 的第一个元素

> 原文:[https://www . geeksforgeeks . org/如何跳过仅 scala 列表中的第一个元素/](https://www.geeksforgeeks.org/how-to-skip-only-first-element-of-list-in-scala/)

在 Scala 中，列表在`scala.collection.immutable`包下定义。列表是包含不可变数据的相同类型元素的集合。让我们看看如何通过跳过 Scala 中的第一项来打印给定列表的元素。

Scala 中的 List 包含许多合适的方法来执行简单的操作，如 head()，tail()，isEmpty()。来到列表，使用 **tail()** 方法跳过列表的第一个元素。
以下是仅跳过列表第一个元素的示例。
 **例:**

```scala
// Scala program to skip only first element of List
import scala.collection.immutable._

// Creating object 
object GFGobject
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating and initializing immutable lists 
        val mylist: List[String] = List("Geeks", "For", "geeks", "is",
                                          "a", "fabulous", "portal")

        println(mylist.tail) 

    }
}
```

**Output:**

```scala
List(For, geeks, is, a, fabulous, portal)

```

**示例:**

```scala
// Scala program to skip only first element of List
import scala.collection.immutable._

// Creating object 
object GFG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
        // range from 10 to 19
        val myList = List.range(10, 19)
        println(myList) 

        println("Using tail() method: " + myList.tail)
    } 
}     
```

**Output:**

```scala
List(10, 11, 12, 13, 14, 15, 16, 17, 18)
Using tail() method: List(11, 12, 13, 14, 15, 16, 17, 18)

```