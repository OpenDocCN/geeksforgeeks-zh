# 在 Scala 中将 Java 字符串集转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-string-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-sequence-in-scala/)

利用 Scala 中 java 的*to eq*方法，可以将一组 Java 字符串转换为 Scala 中的序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("geeks")
        set.add("for")
        set.add("geeks")

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(geeks, for)

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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("i")
        set.add("am an")
        set.add("author")

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(author, i, am an)

```