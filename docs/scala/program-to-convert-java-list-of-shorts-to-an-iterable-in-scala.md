# 将 Java 短路列表转换为 Scala 中可迭代列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-shot-list-to-an-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一个 Java 的 Shorts 列表转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(843)
        list.add(911)
        list.add(1000)

        // Converting list to an Iterable
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(843, 911, 1000)

```

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

        // Creating list of Shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding Shorts to the list
        list.add(-111)
        list.add(-123)
        list.add(-1000)

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(-111, -123, -1000)

```