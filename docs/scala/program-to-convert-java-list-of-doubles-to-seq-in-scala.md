# 在 Scala 中把 Java 双精度列表转换成 Seq 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-of-double-to-seq-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-doubles-to-seq-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 的双精度列表转换成 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(4.34)
        list.add(51.34)
        list.add(2.34)

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(4.34, 51.34, 2.34)

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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(4.15)
        list.add(4.45)
        list.add(4.11)

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(4.15, 4.45, 4.11)

```

**参考:**
[https://alvinalexander . com/Scala/how-to-from-Java-collections-convert-in-Scala-interaction](https://alvinalexander.com/scala/how-to-go-from-java-collections-convert-in-scala-interact)。