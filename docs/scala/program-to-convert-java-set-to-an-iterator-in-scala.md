# 将 Java 集合转换为 Scala 迭代器的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-to-iterator-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-to-an-iterator-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一个 Java 集合转换成 Scala 中的迭代器。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to an iterator in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(9)
        set.add(10)
        set.add(11)

        // Converting set to an iterator 
        val iter = set.toIterator

        // Displays output
        println(iter)

    }
}
```

**Output:**

```scala
non-empty iterator

```

因此，返回一个非空迭代器。这里，首先创建一个集合，利用 *add* 方法向其中添加整数元素。之后利用*到迭代器*的方法将所述集合转换成迭代器。
**例:2#**

```scala
// Scala program to convert Java set 
// to an iterator in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Converting set to an iterator 
        val iter = set.toIterator

        // Displays output
        println(iter)

    }
}
```

**Output:**

```scala
empty iterator

```

它与上面的例子相同，但是这里没有在所述列表中的元素。因此，这里返回了一个空迭代器。