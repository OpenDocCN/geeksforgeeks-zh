# 在 Scala 中将 Java 双精度集合转换为 Iterable 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-double-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-doubles-to-an-iterable-in-scala/)

通过利用 Scala 中 java 的*到*方法，可以将一组 Java 双精度值转换为 Scala 中的 Iterable。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(3.56)
        set.add(9.34)
        set.add(11.67)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(3.56, 9.34, 11.67)

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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(11.22)
        set.add(45.22)
        set.add(69.22)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(45.22, 69.22, 11.22)

```