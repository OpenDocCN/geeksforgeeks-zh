# 在 Scala 中将 Java 浮点集合转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-float-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一组 Java 浮点转换为 Scala 中的 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(2.1f)
        set.add(4.1f)
        set.add(9.1f)

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(2.1, 4.1, 9.1)

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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(6.3f)
        set.add(8.4f)
        set.add(10.1f)

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(8.4, 6.3, 10.1)

```