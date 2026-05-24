# 在 Scala 中将 Java 浮点列表转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-float-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-floats-to-stream-in-scala/)

利用 Scala 中 java 的 to Stream 方法，可以将一个 Java 浮点列表转换为 Scala 中的 Stream。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(6.3f)
        list.add(8.3f)
        list.add(4.3f)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(6.3, ?)

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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(4.9f)
        list.add(4.6f)
        list.add(4.7f)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(4.9, ?)

```