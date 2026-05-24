# 在 Scala 中将 Java 字符串集转换为索引序列的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-set-of-string-to-a-indexed-in-sequence-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-an-indexed-sequence-in-scala/)

通过利用 Scala 中 java 的*到*方法，可以将一组 Java 字符串转换为 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("geeks")
        set.add("for")
        set.add("geeks")

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(geeks, for)

```

因此，返回一个索引序列，但不显示任何字符串的副本。
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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("I")
        set.add("am an")
        set.add("author")

        // Converting set to an Indexed Sequence
        val ind = set.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(author, I, am an)

```

这里，所述集合返回一个索引序列，其中首先显示具有更大长度的字符串，最后显示具有更多字数的字符串。