# 在 Scala 中将 Java 字节列表转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-bytes-list-to-an-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-bytes-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*到*方法，可以将 Java 字节列表转换成 Scala 中的索引序列。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(103)
        list.add(126)
        list.add(111)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(103, 126, 111)

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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(99)
        list.add(123)
        list.add(8)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(99, 123, 8)

```