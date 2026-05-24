# 在 Scala 中将 Java 双精度列表转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-double-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-doubles-to-stream-in-scala/)

利用 Scala 中 java 的 to Stream 方法，可以将双精度的 Java 列表转换为 Scala 中的 Stream。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(4.33)
        list.add(34.33)
        list.add(2.33)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(4.33, ?)

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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(5.67)
        list.add(5.03)
        list.add(5.92)

        // Converting list to Stream 
        val stream = list.toStream

        // Displays Stream
        println(stream)

    }
}
```

**Output:**

```scala
Stream(5.67, ?)

```