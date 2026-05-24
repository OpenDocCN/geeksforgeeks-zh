# 在 Scala 中将 Java 浮点列表转换为 Seq 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-float-to-seq-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-floats-to-seq-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 的 floats 列表转换成 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(2.2f)
        list.add(5.2f)
        list.add(1.2f)

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(2.2, 5.2, 1.2)

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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(4.6f)
        list.add(4.9f)
        list.add(4.4f)

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(4.6, 4.9, 4.4)

```