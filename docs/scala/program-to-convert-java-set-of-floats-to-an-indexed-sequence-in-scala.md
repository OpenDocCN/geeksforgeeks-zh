# 在 Scala 中将 Java 浮点集合转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-float-to-an-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-an-indexed-sequence-in-scala/)

通过利用 Scala 中 java 的*to Indexed eq*方法，可以将一组 Java 浮点转换为 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(3.1f)
        set.add(2.1f)
        set.add(5.1f)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(3.1, 2.1, 5.1)

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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(3.6f)
        set.add(9.2f)
        set.add(1.8f)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(3.6, 9.2, 1.8)

```