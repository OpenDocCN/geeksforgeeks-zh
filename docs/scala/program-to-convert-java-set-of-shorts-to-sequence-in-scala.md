# 在 Scala 中将 Java 短路集转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-sequence-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将 Java 的一组 Shorts 转换成 Scala 中的一个 Sequence。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(1000)
        set.add(990)
        set.add(998)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(998, 1000, 990)

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

        // Creating set of Shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding Shorts to the set
        set.add(-100)
        set.add(-1000)
        set.add(-99)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(-99, -100, -1000)

```