# 在 Scala 中将 Java 双精度列表转换为 Iterable 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-of-double-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-doubles-to-an-iterable-in-scala/)

通过在 Scala 中使用 java 的*到*方法，可以在 Scala 中将双精度的 Java 列表转换为 Iterable。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(8.1)
        list.add(9.1)
        list.add(10.1)

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

        // Creating list of doubles in Java
        val list = new java.util.ArrayList[Double]()

        // Adding doubles to the list
        list.add(3.3)
        list.add(2.4)
        list.add(1.1)

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(3.3, 2.4, 1.1)

```