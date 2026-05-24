# 在 Scala 中将 Java 整数列表转换为可迭代列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-of-integer-to-iterative-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-integer-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一个整型的 Java 列表转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of Integer in Java
        val list = new java.util.ArrayList[Int]()

        // Adding Integer to the list
        list.add(8)
        list.add(9)
        list.add(10)

        // Converting list to an Iterable
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(8, 9, 10)

```

因此，返回一个缓冲区，元素以所述列表的顺序出现，并且这里没有消除重复的元素。
**例:2#**

```scala
// Scala program to convert Java list 
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of Integer in Java
        val list = new java.util.ArrayList[Int]()

        // Adding Integer to the list
        list.add(3)
        list.add(2)
        list.add(1)

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(3, 2, 1)

```

这里，所述列表的顺序不正确，因此结果缓冲区的顺序也不正确。