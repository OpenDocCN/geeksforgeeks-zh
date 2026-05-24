# 在 Scala 中把 Java 短路列表转换成序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-short-to-seq-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-seq-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 的 Shorts 列表转换成 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(111)
        list.add(1000)
        list.add(99)

        // Converting list to Sequence 
        val seq = list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(111, 1000, 99)

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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(-777)
        list.add(-1000)
        list.add(-666)

        // Converting list to Sequence 
        val seq = list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(-777, -1000, -666)

```