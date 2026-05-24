# 在 Scala 中将 Java 字节集转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-bytes-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-bytes-to-stream-in-scala/)

利用 Scala 中 java 的 *toStream* 方法，可以将一组 Java 字节转换为 Scala 中的流。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to Stream in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of bytes in Java
        val set = new java.util.HashSet[Byte]()

        // Adding bytes to the set
        set.add(100)
        set.add(125)
        set.add(99)

        // Converting set to Stream 
        val stream = set.toStream

        // Displays Stream 
        println(stream)

    }
}
```

**Output:**

```scala
Stream(99, ?)

```

**例:2#**

```scala
// Scala program to convert Java set 
// to Stream in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of bytes in Java
        val set = new java.util.HashSet[Byte]()

        // Adding bytes to the set
        set.add(-28)
        set.add(-125)
        set.add(-12)

        // Converting set to Stream 
        val stream= set.toStream

        // Displays Stream 
        println(stream)

    }
}
```

**Output:**

```scala
Stream(-28, ?)

```