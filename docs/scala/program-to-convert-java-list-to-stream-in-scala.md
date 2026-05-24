# 在 Scala 中将 Java 列表转换为 Stream 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-stream-in-scala/)

利用 Scala 中 java 的 *toStream* 方法，可以将一个 Java 列表转换成 Scala 中的 Stream。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to Stream in Scala

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

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(5, ?)

```

因此，返回一个整数流。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后，使用*至流*方法将所述列表转换为流。
**例:2#**

```scala
// Scala program to convert Java list 
// to Stream in Scala

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
        list.add(1)

        // Converting list to a Stream
        val stream= list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(5, ?)

```

它与上面的示例相同，但是这里在所述列表中又添加了一个元素，然后以流的形式返回。