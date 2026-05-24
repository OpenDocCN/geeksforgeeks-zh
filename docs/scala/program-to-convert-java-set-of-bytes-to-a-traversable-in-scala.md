# 在 Scala 中将 Java 字节集转换为可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-bytes-to-a-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-bytes-to-a-traversable-in-scala/)

利用 Scala 中 java 的 *toTraversable* 方法，可以将一组 Java 字节转换为 Scala 中的可遍历集合。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

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
        set.add(123)
        set.add(111)
        set.add(127)

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(123, 111, 127)

```

**例:2#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

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
        set.add(-126)
        set.add(-111)
        set.add(-99)

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(-99, -126, -111)

```