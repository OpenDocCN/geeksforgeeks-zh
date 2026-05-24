# 在 Scala 中将 Java 浮点集合转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-float-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-sequence-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一组 Java 浮点转换为 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to Sequence in Scala

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
        set.add(1.2f)
        set.add(3.2f)
        set.add(8.2f)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(8.2, 3.2, 1.2)

```

**例:2#**

```scala
// Scala program to convert Java set 
// to Sequence in Scala

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
        set.add(2.4f)
        set.add(2.6f)
        set.add(2.1f)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(2.6, 2.1, 2.4)

```