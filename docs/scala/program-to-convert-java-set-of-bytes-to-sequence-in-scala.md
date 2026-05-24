# 在 Scala 中将 Java 字节集转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-bytes-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-bytes-to-sequence-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一组 Java 字节转换为 Scala 中的一个序列。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to Sequence in Scala

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
        set.add(111)
        set.add(126)
        set.add(98)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(98, 126, 111)

```

**例:2#**

```scala
// Scala program to convert Java set 
// to Sequence in Scala

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
        set.add(-103)
        set.add(-126)
        set.add(-89)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(-103, -89, -126)

```