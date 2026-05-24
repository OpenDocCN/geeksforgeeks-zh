# 如何在 Scala 中获取 List 的第一个元素

> 原文:[https://www . geeksforgeeks . org/如何获取 scala 列表中的第一个元素/](https://www.geeksforgeeks.org/how-to-get-the-first-element-of-list-in-scala/)

在 Scala 中，列表是在 Scala . collection . imbible package 下定义的。列表是包含不可变数据的相同类型元素的集合。让我们看看如何在 Scala 中获得给定列表的第一个元素。
Scala 中的 List 包含许多合适的方法来执行简单的操作，比如 head()，tail()，isEmpty()。来到列表，head()方法用于获取列表的 head/top 元素。
下面是获取列表第一个元素的例子。

**例:**

## 斯卡拉

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
        val mylist: List[String] = List("Geeks", "For", "geeks", "is",
                                        "a", "fabulous", "portal")

        println("The head of the list is:")
        println(mylist.head)
    }
}
```

**输出:**

```scala
The head of the list is:
Geeks
```

**例:**

## 斯卡拉

```scala
// Scala program to creating a uniform list
import scala.collection.immutable._

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        // Repeats Scala three times.
        val myList = List.range(10, 19)
        println(myList)

        println("First element is: " + myList.head)
    }
}
```

**输出:**

```scala
List(10, 11, 12, 13, 14, 15, 16, 17, 18)
First element is: 10
```