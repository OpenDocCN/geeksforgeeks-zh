# 在 Scala 中将 Java 短路列表转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-short-to-an-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*to Indexed eq*方法，可以将 Java 的 Shorts 列表转换为 Scala 中的索引序列。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to an Indexed Sequence in Scala

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
        list.add(100)
        list.add(1000)
        list.add(301)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(100, 1000, 301)

```

**例:2#**

```scala
// Scala program to convert Java list 
// to an Indexed Sequence in Scala

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
        list.add(-111)
        list.add(-1000)
        list.add(-123)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(-111, -1000, -123)

```