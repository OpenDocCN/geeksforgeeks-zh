# 在 Scala 中将 Java 字符集转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符集-到索引序列-in-scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一组 Java 字符转换成 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('c')
        set.add('d')
        set.add('e')

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(c, d, e)

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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('b')
        set.add('c')
        set.add('a')

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(a, b, c)

```

这里，所述集合不是以适当的顺序陈述的，但是结果输出是以适当的顺序陈述的。