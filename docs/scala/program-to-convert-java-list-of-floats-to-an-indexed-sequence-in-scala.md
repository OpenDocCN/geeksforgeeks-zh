# 在 Scala 中将 Java 浮点列表转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-of-float-to-an-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-floats-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*to Indexed eq*方法，可以将 Java 的浮点列表转换为 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(1.1f)
        list.add(2.1f)
        list.add(3.1f)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(1.1, 2.1, 3.1)

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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(9.6f)
        list.add(4.5f)
        list.add(8.3f)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(9.6, 4.5, 8.3)

```