# 在 Scala 中将 Java 短集转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将 Java 的一组 Shorts 转换成 Scala 中的一个 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set
// to a Vector in Scala

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
        set.add(899)
        set.add(999)

        // Converting set to a Vector 
        val vec = set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(899, 999, 1000)

```

**例:2#**

```scala
// Scala program to convert Java set
// to a Vector in Scala

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
        set.add(999)
        set.add(-233)

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(-1000, 999, -233)

```