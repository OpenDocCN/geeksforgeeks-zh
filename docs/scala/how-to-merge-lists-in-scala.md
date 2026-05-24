# 如何在 Scala 中合并列表

> 原文:[https://www.geeksforgeeks.org/how-to-merge-lists-in-scala/](https://www.geeksforgeeks.org/how-to-merge-lists-in-scala/)

一个[列表](https://www.geeksforgeeks.org/scala-lists/)是一个包含不可变数据的集合。列表表示 Scala 中的链表。Scala 列表类保存了一个有序的、线性的项目列表。列表是不可变的，代表一个链表。
**列表语法:**

```scala
val variable_name: List[type] = List(item1, item2, item3)
or
val variable_name = List(item1, item2, item3)
```

以下是合并列表的三种不同方式:

*   使用++
*   使用:::
*   使用 concat

以下是在 Scala 中合并两个列表的各种方法:

### 通过使用++方法

**例:**

## 斯卡拉

```scala
// Scala program to merge lists

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        // Creating Lists
        val a = List("geeks", "for", "geeks")
        val b = List("is", "a", "computer science", "portal")
        val c = List("for", "geeks")

        // Merging Lists
        val d = a ++ b ++ c
        println("After merging lists ")
        println(d)
    }
}    

```

**Output:** 

```scala
After merging lists 
List(geeks, for, geeks, is, a, computer science, portal, for, geeks)
```