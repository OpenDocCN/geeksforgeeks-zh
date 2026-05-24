# 在 Scala 中将 Java 短裤集合转换为可迭代的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-an-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将一组 Java 短裤转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(1000)
        set.add(-234)
        set.add(999)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(999, 1000, -234)

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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(-1000)
        set.add(104)
        set.add(99)

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(99, -1000, 104)

```