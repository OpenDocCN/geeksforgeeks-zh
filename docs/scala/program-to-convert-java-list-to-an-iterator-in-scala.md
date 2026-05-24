# 将 Java 列表转换成 Scala 中迭代器的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-iterator-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-an-iterator-in-scala/)

利用 Scala 中 java 的 *toIterator* 方法，可以将 Java 列表转换成 Scala 中的迭代器。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to iterator in Scala

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

        // Converting list to an iterator 
        val iter = list.toIterator

        // Displays output
        println(iter)

    }
}
```

**Output:**

```scala
non-empty iterator

```

因此，返回一个非空迭代器。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后利用*到迭代器*的方法将所述列表转换成迭代器。
**例:2#**

```scala
// Scala program to convert Java list 
// to iterator in Scala

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

        // Converting list to an iterator 
        val iter = list.toIterator

        // Displays output
        println(iter)

    }
}
```

**Output:**

```scala
empty iterator

```

它与上面的例子相同，但是这里返回了一个空的迭代器，因为这里声明的列表是空的。