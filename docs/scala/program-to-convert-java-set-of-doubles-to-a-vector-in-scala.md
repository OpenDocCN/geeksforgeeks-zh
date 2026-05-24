# 在 Scala 中将 Java 双精度集合转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-double-to-a-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-doubles-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一组 Java 双精度值转换为 Scala 中的一个 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(3.4)
        set.add(6.4)
        set.add(1.4)

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(1.4, 6.4, 3.4)

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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(4.2)
        set.add(4.5)
        set.add(4.3)

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(4.5, 4.3, 4.2)

```