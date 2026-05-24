# 在 Scala 中将 Java 字节集转换为 Iterable 的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-set-bytes-to-iterable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-bytes-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一组 Java 字节转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of bytes in Java
        val set = new java.util.HashSet[Byte]()

        // Adding bytes to the set
        set.add(126)
        set.add(123)
        set.add(125)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(123, 125, 126)

```

**例:2#**

```scala
// Scala program to convert Java set
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of bytes in Java
        val set = new java.util.HashSet[Byte]()

        // Adding bytes to the set
        set.add(-123)
        set.add(-111)
        set.add(-126)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(-123, -126, -111)

```