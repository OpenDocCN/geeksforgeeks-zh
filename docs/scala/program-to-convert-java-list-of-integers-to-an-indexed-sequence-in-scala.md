# 在 Scala 中将 Java 整数列表转换为索引序列的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-list-integer-to-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-integers-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*到*方法，可以将 Java 列表转换成 Scala 中的索引序列。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(1)
        list.add(2)
        list.add(3)

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(1, 2, 3)

```

因此，返回一个索引序列。
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

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(9)
        list.add(4)
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
Vector(9, 4, 8)

```

这里，所陈述的列表没有按正确的顺序排列，因此结果输出也没有按正确的顺序排列。