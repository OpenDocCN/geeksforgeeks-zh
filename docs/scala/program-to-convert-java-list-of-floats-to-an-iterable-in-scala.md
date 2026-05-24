# 在 Scala 中将 Java 浮点列表转换为 Iterable 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-float-to-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-floats-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将 Java 的浮点列表转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(8.1f)
        list.add(9.1f)
        list.add(10.1f)

        // Converting list to an Iterable
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(8.1, 9.1, 10.1)

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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(3.4f)
        list.add(2.6f)
        list.add(1.1f)

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(3.4, 2.6, 1.1)

```