# 在 Scala 中将 Java 字符串列表转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-strings-to-stream-in-scala/)

利用 Scala 中 java 的 to Stream 方法，可以将 Java 字符串列表转换为 Scala 中的 Stream。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("geeeks")
        list.add("for")
        list.add("geeks")

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(geeeks, ?)

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

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("i")
        list.add("am an")
        list.add("author")

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(i, ?)

```