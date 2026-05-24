# 在 Scala 中将 Java 短裤集合转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-an-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*to Indexed eq*方法，可以将一组 Java short 转换为 Scala 中的索引序列。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(100)
        set.add(1000)
        set.add(999)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(100, 999, 1000)

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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(-199)
        set.add(-1000)
        set.add(-200)

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(-199, -1000, -200)

```