# 在 Scala 中将 Java 双精度列表转换为可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-double-to-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-doubles-to-traversable-in-scala/)

利用 Scala 中 java 的 *toTraversable* 方法，可以将一个 Java 的双精度列表转换成 Scala 中的 Traversable 集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

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
        list.add(3.5)
        list.add(7.8)
        list.add(9.2)

        // Converting list to a Traversable 
        val tra = list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(3.5, 7.8, 9.2)

```

**例:2#**

```scala
// Scala program to convert Java list
// to a Traversable in Scala

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
        list.add(5.8)
        list.add(8.8)
        list.add(1.8)

        // Converting list to a Traversable 
        val tra= list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(5.8, 8.8, 1.8)

```