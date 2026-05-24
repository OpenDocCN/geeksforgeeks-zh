# 在 Scala 中将 Java 字符列表转换为索引序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符列表-到索引序列-in-scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-characters-to-an-indexed-sequence-in-scala/)

利用 Scala 中 java 的*to Indexed eq*方法，可以将 Java 字符列表转换为 Scala 中的索引序列。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('a')
        list.add('b')
        list.add('c')

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(a, b, c)

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

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('b')
        list.add('c')
        list.add('a')

        // Converting list to an Indexed Sequence 
        val ind = list.toIndexedSeq

        // Displays Indexed Sequence
        println(ind)

    }
}
```

**Output:**

```scala
Vector(b, c, a)

```

这里，所陈述的列表没有按正确的顺序排列，因此结果输出也没有按正确的顺序排列。