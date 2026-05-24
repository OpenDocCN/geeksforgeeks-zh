# 在 Scala 中将 Java 整数集转换为索引序列的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-set-integer-to-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-integers-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一组 Java 整数转换成 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of integers in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(9)
        set.add(10)
        set.add(11)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(9, 10, 11)

```

因此，返回一个索引序列。
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

        // Creating set of integers in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(7)
        set.add(3)
        set.add(9)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(3, 7, 9)

```

这里，所述集合不是以适当的顺序陈述的，但是结果输出是以适当的顺序陈述的。