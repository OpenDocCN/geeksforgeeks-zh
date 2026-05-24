# 在 Scala 中将 Java 短集转换为可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-a-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-a-traversable-in-scala/)

通过利用 Scala 中 java 的 *toTraversable* 方法，可以将一个 Java shots 集合转换为 Scala 中的可遍历集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(1000)
        set.add(123)
        set.add(999)

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(999, 1000, 123)

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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(-1000)
        set.add(-110)
        set.add(99)

        // Converting set to a Traversable 
        val tra= set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(99, -1000, -110)

```