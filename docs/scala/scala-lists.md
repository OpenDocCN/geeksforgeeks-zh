# Scala 列表

> 原文:[https://www.geeksforgeeks.org/scala-lists/](https://www.geeksforgeeks.org/scala-lists/)

一个**列表**是一个包含不可变数据的集合。列表表示 Scala 中的链表。**斯卡拉列表**类保存一个有序的线性项目列表。
以下是 Scala 中列表和数组的区别点:

*   列表是不可变的，而数组在 Scala 中是可变的。
*   列表代表链接列表，而数组是平面的。

**语法:**

```scala
val variable_name: List[type] = List(item1, item2, item3)
or
val variable_name = List(item1, item2, item3)

```

**Scala 中关于 list 的一些要点:**

*   在 Scala 列表中，每个元素必须是相同的类型。
*   列表的实现在构建过程中内部使用可变状态。
*   在 Scala 中，列表是在 Scala . collection . imbible package 下定义的。
*   列表有各种各样的方法来添加、预先添加、最大化、最小化等。加强列表的使用。

**示例:**

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
        val mylist1: List[String] = List("Geeks", "GFG",
                            "GeeksforGeeks", "Geek123")
        val mylist2 = List("C", "C#", "Java", "Scala",
                                        "PHP", "Ruby")

        // Display the value of mylist1
        println("List 1:")
        println(mylist1)

        // Display the value of mylist2 using for loop
        println("\nList 2:")
        for(mylist<-mylist2)
        {
            println(mylist)
        }
    }
}
```

**Output:**

```scala
List 1:
List(Geeks, GFG, GeeksforGeeks, Geek123)

List 2:
C
C#
Java
Scala
PHP
Ruby

```