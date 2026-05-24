# 在 Scala 中将 Java 浮点集合转换为流的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-float-to-stream-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-stream-in-scala/)

利用 Scala 中 java 的 *toStream* 方法，可以将一组 Java 浮点转换为 Scala 中的流。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(4.1f)
        set.add(9.1f)
        set.add(89.1f)

        // Converting set to Stream 
        val stream = set.toStream

        // Displays Stream 
        println(stream)

    }
}
```

**Output:**

```scala
Stream(4.1, ?)

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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(12.34f)
        set.add(12.56f)
        set.add(12.13f)

        // Converting set to Stream 
        val stream= set.toStream

        // Displays Stream 
        println(stream)

    }
}
```

**Output:**

```scala
Stream(12.34, ?)

```