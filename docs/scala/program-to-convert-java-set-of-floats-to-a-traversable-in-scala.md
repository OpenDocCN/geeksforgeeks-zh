# 在 Scala 中将 Java 浮点集合转换为可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-floats-to-a-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-a-traversable-in-scala/)

通过利用 Scala 中 java 的 *toTraversable* 方法，可以将一组 Java 浮点转换为 Scala 中的 Traversable 集合。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(4.1f)
        set.add(7.1f)
        set.add(8.1f)

        // Converting set to a Traversable 
        val tra= set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(4.1, 7.1, 8.1)

```

**例:2#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(5.2f)
        set.add(4.5f)
        set.add(9.2f)

        // Converting set to a Traversable 
        val tra= set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(5.2, 4.5, 9.2)

```