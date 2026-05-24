# 在 Scala 中将 Java 字节列表转换为 Seq 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-bytes-to-seq-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-bytes-to-seq-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 字节列表转换成 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to Sequence in Scala

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
        list.add(127)
        list.add(120)

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(121, 127, 120)

```

**例:2#**

```scala
// Scala program to convert Java list 
// to Sequence in Scala

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
        list.add(-124)
        list.add(-126)
        list.add(-120)

        // Converting list to Sequence 
        val seq = list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(-124, -126, -120)

```