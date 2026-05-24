# 将 Java 列表转换为 Scala 中可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-traversable-in-scala/)

利用 Scala 中 java 的 *toTraversable* 方法，可以将一个 Java 列表转换成 Scala 中的 Traversable 集合。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(5)
        list.add(6)
        list.add(7)

        // Converting list to a Traversable 
        val tra = list.toTraversable

        // Displays Traversable
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(5, 6, 7)

```

因此，返回一个整数缓冲区。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后，使用*到可遍历*方法将所述列表转换为可遍历集合。
**例:2#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(3)
        list.add(1)
        list.add(2)

        // Converting list to a Traversable 
        val tra = list.toTraversable

        // Displays Traversable
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(3, 1, 2)

```

它与上面的示例相同，但是这里所述的列表没有按正确的顺序排列，并且返回的集合也没有按正确的顺序排列。