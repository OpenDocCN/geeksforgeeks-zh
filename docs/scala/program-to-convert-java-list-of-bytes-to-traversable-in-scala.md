# 在 Scala 中将 Java 字节列表转换为可遍历的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-bytes-list-to-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-bytes-to-traversable-in-scala/)

利用 Scala 中 java 的 *toTraversable* 方法，可以将 Java 字节列表转换为 Scala 中的 Traversable 集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(121)
        list.add(111)
        list.add(125)

        // Converting list to a Traversable 
        val tra= list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(121, 111, 125)

```

**例:2#**

```scala
// Scala program to convert Java list
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(-122)
        list.add(-126)
        list.add(-100)

        // Converting list to a Traversable 
        val tra= list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(-122, -126, -100)

```