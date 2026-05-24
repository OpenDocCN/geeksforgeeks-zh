# 在 Scala 中将 Java 字节集转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字节集到索引序列中的 scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-bytes-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一组 Java 字节转换成 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set
// to an Indexed Sequence in Scala

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
        set.add(121)
        set.add(35)
        set.add(126)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(35, 121, 126)

```

**例:2#**

```scala
// Scala program to convert Java set
// to an Indexed Sequence in Scala

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
        set.add(-125)
        set.add(-10)
        set.add(-126)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(-10, -125, -126)

```