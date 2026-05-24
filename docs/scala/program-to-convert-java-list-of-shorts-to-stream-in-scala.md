# 在 Scala 中将 Java 短路列表转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-short-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-stream-in-scala/)

利用 Scala 中 java 的 to Stream 方法，可以将一个 Java shots 列表转换为 Scala 中的 Stream。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(888)
        list.add(1000)
        list.add(666)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(888, ?)

```

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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(-99)
        list.add(-1000)
        list.add(-32)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(-99, ?)

```