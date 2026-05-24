# 在 Scala 中将 Java 双精度集合转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-double-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-doubles-to-sequence-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一组 Java 双精度转换为 Scala 中的一个序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(3.2)
        set.add(51.2)
        set.add(63.2)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(3.2, 51.2, 63.2)

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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(6.34)
        set.add(6.23)
        set.add(6.91)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(6.91, 6.23, 6.34)

```